---
layout: default
title: Event hooks
nav_order: 1
grand_parent: Customizing/Extending Masa
parent: Events
last_modified_date: 11-01-2021 10:00
permalink: /customizing-extending-masa/events/event-hooks/
---

# Event hooks
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

- TOC
{:toc}

## Standard events

| Event                           | Description |
| :------------------------------ | :---------- |
| standard404Handler              |             |
| standard404Validator            |             |
| standardDoActionsHandler        |             |
| standardDoResponseHandler       |             |
| standardEnableLockdownHandler   |             |
| standardEnableLockdownValidator |             |
| standardFileTranslationHandler  |             |
| standardFileTranslator          |             |
| standardForceSSLHandler         |             |
| standardForceSSLValidator       |             |
| standardJSONTranslator          |             |
| standardLinkTranslationHandler  |             |
| standardLinkTranslator          |             |
| standardMobileHandler           |             |
| standardMobileValidator         |             |
| standardPostLogoutHandler       |             |
| standardRequireLoginHandler     |             |
| standardRequireLoginValidator   |             |
| standardSetContentHandler       |             |
| standardSetIsOnDisplayHandler   |             |
| standardSetLocaleHandler        |             |
| standardSetPermissionsHandler   |             |
| standardSetPreviewHandler       |             |
| standardTrackSessionHandler     |             |
| standardTrackSessionValidator   |             |
| standardTranslationHandler      |             |
| standardWrongDomainValidator    |             |
| standardWrongFilenameHandler    |             |
| standardWrongFilenameValidato   |             |

## App-related events

### Analogous CFML Application Events

| Event                   | Analogous CFML Application Event | Description                                                                                    |
| :---------------------- | :------------------------------- | :--------------------------------------------------------------------------------------------- |
| onApplicationLoad       | onApplicationStart               |                                                                                                |
| onGlobalSessionStart    | onRequestStart                   | announced only if session management is enabled, and request.doMuraGlobalSessionStart is true. |
| onGlobalSessionEnd      | onSessionEnd                     | announced only if session.siteid is not defined.                                               |
| onSiteSessionEnd        | onSessionEnd                     | announced only if session.siteid is defined.                                                   |
| onGlobalRequestStart    | onRequestStart                   |                                                                                                |
| onGlobalRequestEnd      | onRequestEnd                     |                                                                                                |
| onGlobalMissingTemplate | onMissingTemplate                | announced only if siteid is not defined in the event.                                          |
| onSiteMissingTemplate   | onMissingTemplate                | announced only if siteid is defined in the event.                                              |
| onGlobalError           | onError                          | announced only if siteid is not defined in the event.                                          |
| onSiteError             | onError                          | announced only if siteid is defined in the event.                                              |

### Administration Events

| Event                        | Description |
| :--------------------------- | :---------- |
| onBeforeAutoUpdate           |             |
| onAfterAutoUpdate            |             |
| onGlobalThreatDetect         |             |
| onAdminRequestStart          |             |
| onAdminRequestEnd            |             |
| onSiteDeploy                 |             |
| onBeforeSiteDeploy           |             |
| onAfterSiteDeploy            |             |
| onAfterSiteDeployRender      |             |
| onSiteCopy                   |             |
| onBeforeSiteUpdate           |             |
| onBeforeSiteSave             |             |
| onAfterSiteUpdate            |             |
| onAfterSiteSave              |             |
| onBeforeSiteDelete           |             |
| onAfterSiteDelete            |             |
| onBeforeSiteCreate           |             |
| onAfterSiteCreate            |             |
| onBeforeSiteEmptyTrash       |             |
| onBeforeGlobalEmptyTrash     |             |
| onAfterSiteEmptyTrash        |             |
| onAfterGlobalEmptyTrash      |             |
| onBeforeProxyBundleDeploy    |             |
| onAfterProxyBundleDeploy     |             |
| onBeforeChangeSetPublish     |             |
| onAfterChangeSetPublish      |             |
| onAfterChangeSetPublishError |             |

### Administration Area Rendering Events

| Event                                 | Description |
| :------------------------------------ | :---------- |
| onDashboardReplacement                |             |
| onDashboardPrimaryTop                 |             |
| onDashboardPrimaryBottom              |             |
| onDashboardSidebarTop                 |             |
| onDashboardSidebarBottom              |             |
| onAdminNavMainRender                  |             |
| onFEToolbarExtensionRender            |             |
| onAdminHTMLHeadRender                 |             |
| onAdminHTMLFootRender                 |             |
| onAdminMFAChallengeRender             |             |
| onContentSecondaryNavRender           |             |
| on{Type}SecondaryNavRender            |             |
| on{Type}{Subtype}SecondaryNavRender   |             |
| onNewContentMenuRender                |             |
| on{Type}{Subtype}NewContentMenuRender |             |

### JSON API Events

| Event                        | Description |
| :--------------------------- | :---------- |
| onAPIResponse                |             |
| on{Type}APIResponse          |             |
| on{Type}{Subtype}APIResponse |             |
| onAPIError                   |             |
| onSiteAsyncRequestStart      |             |
| onAsyncRenderStart           |             |

## Content-related events

### Content Editing Events

| Event                         | Description |
| :---------------------------- | :---------- |
| onBeforeContentSave           |             |
| onBefore{Type}Save            |             |
| onBefore{Type}{Subtype}Save   |             |
| onAfterContentSave            |             |
| onAfter{Type}Save             |             |
| onAfter{Type}{Subtype}Save    |             |
| onBeforeContentDelete         |             |
| onBefore{Type}Delete          |             |
| onBefore{Type}{Subtype}Delete |             |
| onContentDelete               |             |
| on{Type}Delete                |             |
| on{Type}{Subtype}Delete       |             |
| onAfterContentDelete          |             |
| onAfter{Type}Delete           |             |
| onAfter{Type}{Subtype}Delete  |             |

### Content Version History Events

| Event                                       | Description |
| :------------------------------------------ | :---------- |
| onContentDeleteVersionHistory               |             |
| onBeforeContentDeleteVersionHistory         |             |
| onBefore{Type}DeleteVersionHistory          |             |
| onBefore{Type}{Subtype}DeleteVersionHistory |             |
| onBefore{Type}{Subtype}DeleteVersion        |             |
| on{Type}DeleteVersionHistory                |             |
| on{Type}{Subtype}DeleteVersionHistory       |             |
| onAfterContentDeleteVersionHistory          |             |
| onAfter{Type}DeleteVersionHistory           |             |
| onAfter{Type}{Subtype}DeleteVersionHistory  |             |
| onContentDeleteVersion                      |             |
| onBeforeContentDeleteVersion                |             |
| onBefore{Type}DeleteVersion                 |             |
| onBefore{Type}{Subtype}DeleteVersion        |             |
| onAfterContentDeleteVersion                 |             |
| onAfter{Type}DeleteVersion                  |             |
| onAfter{Type}{Subtype}DeleteVersion         |             |

### Content Rendering Events

| Event                              | Description      |
| :--------------------------------- | :--------------- |
| onSite404                          |                  |
| onSiteCKEditorConfigRender         |                  |
| onSiteCKFinderConfig               | _Removed in 7.3_ |
| onContentEdit                      |                  |
| on{Type}Edit                       |                  |
| on{Type}{Subtype}Edit              |                  |
| onContentEditMessageRender         |                  |
| on{Type}EditMessageRender          |                  |
| on{Type}{Subtype}EditMessageRender |                  |
| onFeedEditMessageRender            |                  |

### Comments Events

| Event                       | Description |
| :-------------------------- | :---------- |
| onBeforeCommentCreate       |             |
| onBeforeCommentSave         |             |
| onBeforeCommentUpdate       |             |
| onBeforeCommentDelete       |             |
| onAfterCommentCreate        |             |
| onAfterCommentSave          |             |
| onAfterCommentUpdate        |             |
| onAfterCommentDelete        |             |
| onBeforeCommentUndelete     |             |
| onAfterCommentUndelete      |             |
| onBeforeCommentFlag         |             |
| onAfterCommentFlag          |             |
| onBeforeCommentMarkAsSpam   |             |
| onAfterCommentMarkAsSpam    |             |
| onBeforeCommentUnMarkAsSpam |             |
| onAfterCommentUnMarkAsSpam  |             |

### Category Events

| Event                  | Description |
| :--------------------- | :---------- |
| onBeforeCategoryCreate |             |
| onBeforeCategorySave   |             |
| onBeforeCategoryUpdate |             |
| onBeforeCategoryDelete |             |
| onAfterCategoryCreate  |             |
| onAfterCategorySave    |             |
| onAfterCategoryUpdate  |             |
| onAfterCategoryDelete  |             |

### File-specific Events

| Event                     | Description  |
| :------------------------ | :----------- |
| onFileEdit                |              |
| onFileDefaultEdit         |              |
| onBeforeFileCache         |              |
| onFileCache               |              |
| onAfterFileCache          |              |
| onFileCacheDelete         |              |
| onBeforeFileCacheDelete   |              |
| onAfterFileCacheDelete    |              |
| onBeforeFileRender        |              |
| onAfterFileRender         |              |
| onBeforeFilenameCreate    |              |
| onAfterFilenameCreate     |              |
| onBeforeImageManipulation |              |
| onAfterImageManipulation  |              |
| onAfterFileResize         | _New in 7.3_ |
| onAfterFileDuplicate      | _New in 7.3_ |
| onAfterFileRotate         | _New in 7.3_ |
| onAfterFileCrop           | _New in 7.3_ |
| onAfterFileUpload         | _New in 7.3_ |
| onAfterFileEdit           | _New in 7.3_ |
| onAfterFileUpdate         | _New in 7.3_ |
| onAfterFileDelete         | _New in 7.3_ |
| onAfterFileRename         | _New in 7.3_ |

### Form-specific Events

| Event                           | Description |
| :------------------------------ | :---------- |
| onFormElementBasicTabRender     |             |
| onForm{Subtype}BodyRender       |             |
| onBeforeFormSubmitSave          |             |
| onBeforeForm{Subtype}SubmitSave |             |
| onAfterFormSubmitSave           |             |
| onAfterForm{Subtype}SubmitSave  |             |
| onFormSubmitErrorRender         |             |
| onFormSubmitResponseRender      |             |
| onBeforeFormSubmitRedirect      |             |

### Feed-specific Events

| Event              | Description |
| :----------------- | :---------- |
| onBeforeFeedCreate |             |
| onBeforeFeedSave   |             |
| onBeforeFeedUpdate |             |
| onBeforeFeedDelete |             |
| onFeedCreate       |             |
| onFeedSave         |             |
| onFeedUpdate       |             |
| onFeedDelete       |             |
| onAfterFeedCreate  |             |
| onAfterFeedSave    |             |
| onAfterFeedUpdate  |             |
| onAfterFeedDelete  |             |

## User-related events

### User Editing Events

| Event                       | Description |
| :-------------------------- | :---------- |
| onBeforeUserCreate          |             |
| onBeforeUserUpdate          |             |
| onBeforeUserSave            |             |
| onBeforeUserDelete          |             |
| onBeforeUser{Subtype}Create |             |
| onBeforeUser{Subtype}Update |             |
| onBeforeUser{Subtype}Save   |             |
| onBeforeUser{Subtype}Delete |             |
| onUserCreate                |             |
| onUserUpdate                |             |
| onUserSave                  |             |
| onUserDelete                |             |
| onAfterUserCreate           |             |
| onAfterUserUpdate           |             |
| onAfterUserSave             |             |
| onAfterUserDelete           |             |
| onAfterUser{Subtype}Create  |             |
| onAfterUser{Subtype}Update  |             |
| onAfterUser{Subtype}Save    |             |
| onAfterUser{Subtype}Delete  |             |

### Group Editing Events

| Event                        | Description |
| :--------------------------- | :---------- |
| onBeforeGroupCreate          |             |
| onBeforeGroupUpdate          |             |
| onBeforeGroupSave            |             |
| onBeforeGroupDelete          |             |
| onBeforeGroup{Subtype}Create |             |
| onBeforeGroup{Subtype}Update |             |
| onBeforeGroup{Subtype}Save   |             |
| onBeforeGroup{Subtype}Delete |             |
| onGroupCreate                |             |
| onGroupUpdate                |             |
| onGroupSave                  |             |
| onGroupDelete                |             |
| onGroup{Subtype}Create       |             |
| onGroup{Subtype}Update       |             |
| onGroup{Subtype}Save         |             |
| onGroup{Subtype}Delete       |             |
| onAfterGroup{Subtype}Create  |             |
| onAfterGroup{Subtype}Update  |             |
| onAfterGroup{Subtype}Save    |             |
| onAfterGroup{Subtype}Delete  |             |

### Group & User Rendering Events

| Event       | Description |
| :---------- | :---------- |
| onGroupEdit |             |
| onUserEdit  |             |

### Login Related Events

| Event                     | Description |
| :------------------------ | :---------- |
| onSiteLogin               |             |
| onSiteLoginSuccess        |             |
| onSiteLoginFailure        |             |
| onSiteLoginBlocked        |             |
| onSiteLogout              |             |
| onBeforeSiteLogout        |             |
| onAfterSiteLogout         |             |
| onGlobalLogin             |             |
| onGlobalLoginSuccess      |             |
| onGlobalLoginFailure      |             |
| onGlobalLoginBlocked      |             |
| onGlobalLogout            |             |
| onBeforeGlobalLogout      |             |
| onAfterGlobalLogout       |             |
| onSiteEditProfileRender   |             |
| onSiteLoginPromptRender   |             |
| onContentDenialRender     |             |
| onAdminMFAChallengeRender |             |
| onSiteMFAChallengeRender  |             |
| onMFAAttemptChallenge     |             |

## Custom events
