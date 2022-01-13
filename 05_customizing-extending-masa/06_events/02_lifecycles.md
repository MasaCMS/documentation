---
layout: default
title: Lifecycles
nav_order: 2
grand_parent: Customizing/Extending Masa
parent: Events
last_modified_date: 11-01-2021 10:00
permalink: /customizing-extending-masa/events/lifecycles/
---

# Lifecycle

A lifecycle is a series of events that get triggerd on every request. Masa CMS has two lifecycle in use:

* [Front-end lifecyle](/customizing-extending-masa/events/lifecycles/#front-end-lifecycle)
* [Administrator lifecycle](/customizing-extending-masa/events/lifecycles/#front-end-lifecycle)

## Front-end lifecycle

The Front-end lifecycle is executed on every request to a site in Masa CMS.

```
onGlobalRequestStart
    onSiteRequestInit
    onSiteRequestStart

        standardEnableLockdownValidator
            standardEnableLockdownHandler (if lockdown enabled)

        standardSetContentHandler
            ( if `previewid` exists )
            standardSetPreviewHandler 
            ( else )
            standardSetAdTrackingHandler

            standardWrongFilenameValidator
                standardWrongFilenameHandler (if wrong filename)

            standard404Validator
            standard404Handler (if content item not found)
                onSite404 

        standardWrongDomainValidator
            standardWrongDomainHandler (if invalid domain)

        standardTrackSessionValidator
            standardTrackSessionHandler (if session tracking enabled)

        standardSetIsOnDisplayHandler
        standardDoActionsHandler (checks `doaction` e.g., login, logout, etc.)

        standardSetPermissionsHandler
        standardRequireLoginValidator
            standardRequireLoginHandler (if login required)

        standardSetLocaleHandler
        standardMobileValidator
            standardMobileHandler (if `request.muraMobileRequest` and no `altTheme`)

        standardSetCommentPermissions

        standardDoResponseHandler
            standardForceSSLValidator
                standardForceSSLHandler (if necessary)

            onRenderStart

                ( if content type is link )
                standardLinkTranslationHandler
                ( else if content type is file )
                standardFileTranslationHandler
                    standardFileTranslator
                        onBeforeFileRender
                        onAfterFileRender
                ( else )
                standardTranslationHandler
                    ( if `returnformat` is JSON )
                    standardJSONTranslator
                        onAPIResponse
                        on{Type}APIResponse
                        on{Type}{Subtype}APIResponse
                        onAPIError (if an error occurs)

                    ( else )
                    standardHTMLTranslator
                        ( if event('display') is `search` )
                        onSiteSearchRender

                        ( else if event('display') is `editprofile` )
                        onSiteEditProfileRender

                        ( else if event('display') is `login` )
                        onSiteLoginPromptRender

                        ( else if content is restricted and user not allowed )
                        onContentDenialRender

                        ( else if content is not on display )
                        onContentOfflineRender

                        ( else if `m.event('display')` is not an empty string )
                        onDisplayRender

                        ( else )
                        on{Type}{Subtype}BodyRender
                        on{Type}BodyRender

            onRenderEnd

    onSiteRequestEnd
onGlobalRequestEnd
```

## Administrator lifecycle

The Administrator lifecycle is executed on every request to the Masa CMS Administrator.

```
onGlobalRequestStart
    onAdminRequestStart
    
        onAdminHTMLHeadRender
    
            onAdminMFAChallengeRender
        
            onDashboardReplacement
        
            onDashboardPrimaryTop
            onDashboardPrimaryBottom
            onDashboardSidebarTop
            onDashboardSidebarBottom
        
            onAdminNavMainRender
            onFEToolbarExtensionRender
            
            on{Type}SecondaryNavRender
            on{Type}{Subtype}SecondaryNavRender
        
            on{Type}{Subtype}NewContentMenuRender
            onNewContentMenuRender
    
        onAdminHTMLFootRender
    
    onAdminRequestEnd
onGlobalRequestEnd
```