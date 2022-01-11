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
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

- TOC
{:toc}

## Front-end request lifecycle

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
                        onAPIError  (if an error occurs)

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

## Admin request lifecycle

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