# Renovate composer dependency updates doesn't respect filtering #33266

## Current behavior

Renovate composer dependency (package releases lookup?) ignores repository filtering & priorities, checking a user defined repository for all packages instead of just the filtered one. It's not clear of repository priority is respected.

## Expected behavior

When a composer repository has an "only/exclude" filter on it, that filtering should be respected.

## Link to the Renovate issue or Discussion

[#33266](https://github.com/renovatebot/renovate/discussions/33266)

```
 INFO: Repository started (repository=test/renovate-composer-filtering)
       "renovateVersion": "39.82.3"
DEBUG: Using localDir: /builds/it-internal/renovate-runner/renovate/repos/gitlab/test/renovate-composer-filtering (repository=test/renovate-composer-filtering)
DEBUG: PackageFiles.clear() - Package files deleted (repository=test/renovate-composer-filtering)
DEBUG: hostRules: applying Bearer authentication for version-control.it.su.org.au (repository=test/renovate-composer-filtering)
DEBUG: Using queue: host=version-control.it.su.org.au, concurrency=16 (repository=test/renovate-composer-filtering)
DEBUG: test/renovate-composer-filtering default branch = main (repository=test/renovate-composer-filtering)
DEBUG: Enabling Git FS (repository=test/renovate-composer-filtering)
DEBUG: Using http URL: https://version-control.it.su.org.au/test/renovate-composer-filtering.git (repository=test/renovate-composer-filtering)
DEBUG: Repository cache is restored from revision 13 (repository=test/renovate-composer-filtering)
DEBUG: Resetting npmrc (repository=test/renovate-composer-filtering)
DEBUG: Resetting npmrc (repository=test/renovate-composer-filtering)
DEBUG: checkOnboarding() (repository=test/renovate-composer-filtering)
DEBUG: isOnboarded() (repository=test/renovate-composer-filtering)
DEBUG: findPr(renovate/configure, Configure Renovate, !open) (repository=test/renovate-composer-filtering)
DEBUG: findPr(renovate/configure, chore: Configure Renovate, !open) (repository=test/renovate-composer-filtering)
DEBUG: Checking cached config file name (repository=test/renovate-composer-filtering)
DEBUG: Existing config file confirmed (repository=test/renovate-composer-filtering)
DEBUG: Repository config (repository=test/renovate-composer-filtering)
       "fileName": "renovate.json",
       "config": {
         "$schema": "https://docs.renovatebot.com/renovate-schema.json",
         "extends": ["config:recommended"],
         "labels": ["2 Security"],
         "branchConcurrentLimit": 3,
         "enabledManagers": ["gitlabci", "gitlabci-include", "composer"]
       }
DEBUG: Repo is onboarded (repository=test/renovate-composer-filtering)
DEBUG: migrateAndValidate() (repository=test/renovate-composer-filtering)
DEBUG: No config migration necessary (repository=test/renovate-composer-filtering)
DEBUG: Found repo ignorePaths (repository=test/renovate-composer-filtering)
       "ignorePaths": [
         "**/node_modules/**",
         "**/bower_components/**",
         "**/vendor/**",
         "**/examples/**",
         "**/__tests__/**",
         "**/test/**",
         "**/tests/**",
         "**/__fixtures__/**"
       ]
DEBUG: No vulnerability alerts found (repository=test/renovate-composer-filtering)
DEBUG: findIssue(Dependency Dashboard) (repository=test/renovate-composer-filtering)
DEBUG: No baseBranches (repository=test/renovate-composer-filtering)
DEBUG: extract() (repository=test/renovate-composer-filtering)
DEBUG: Cached extract for sha=e8476e43e955065227c31ffcbc621200dd9b8a0f is valid and can be used (repository=test/renovate-composer-filtering)
DEBUG: Deleted cached dep updates (repository=test/renovate-composer-filtering)
 INFO: Dependency extraction complete (repository=test/renovate-composer-filtering, baseBranch=main)
       "stats": {
         "managers": {"composer": {"fileCount": 1, "depCount": 2}},
         "total": {"fileCount": 1, "depCount": 2}
       }
DEBUG: GET https://version-control.it.su.org.au/api/v4/group/92/-/packages/composer/p2/bjeavons/zxcvbn-php.json = (code=ERR_NON_2XX_3XX_RESPONSE, statusCode=404 retryCount=0, duration=124) (repository=test/renovate-composer-filtering)
DEBUG: PackageFiles.add() - Package file saved for base branch (repository=test/renovate-composer-filtering, baseBranch=main)
DEBUG: Package releases lookups complete (repository=test/renovate-composer-filtering, baseBranch=main)
DEBUG: branchifyUpgrades (repository=test/renovate-composer-filtering)
DEBUG: detectSemanticCommits() (repository=test/renovate-composer-filtering)
DEBUG: semanticCommits: returning "disabled" from cache (repository=test/renovate-composer-filtering)
DEBUG: 1 flattened updates found: bjeavons/zxcvbn-php (repository=test/renovate-composer-filtering)
DEBUG: Returning 1 branch(es) (repository=test/renovate-composer-filtering)
DEBUG: config.repoIsOnboarded=true (repository=test/renovate-composer-filtering)
DEBUG: packageFiles with updates (repository=test/renovate-composer-filtering, baseBranch=main)
       "config": {
         "composer": [
           {
             "deps": [
               {
                 "currentValue": ">=8.2",
                 "currentVersion": "8.4.3",
                 "currentVersionAgeInDays": 3,
                 "currentVersionTimestamp": "2025-01-17T04:13:34.000Z",
                 "datasource": "github-tags",
                 "depName": "php",
                 "depType": "require",
                 "packageName": "containerbase/php-prebuild",
                 "registryUrl": "https://github.com",
                 "sourceUrl": "https://github.com/containerbase/php-prebuild",
                 "versioning": "composer",
                 "warnings": [],
                 "updates": []
               },
               {
                 "currentValue": "1.3.1",
                 "currentVersion": "1.3.1",
                 "currentVersionAgeInDays": 1126,
                 "currentVersionTimestamp": "2021-12-21T18:37:02.000Z",
                 "datasource": "packagist",
                 "depName": "bjeavons/zxcvbn-php",
                 "depType": "require",
                 "fixedVersion": "1.3.1",
                 "isSingleVersion": true,
                 "lockedVersion": "1.3.1",
                 "packageName": "bjeavons/zxcvbn-php",
                 "registryUrl": "https://packagist.org",
                 "registryUrls": [
                   "https://version-control.it.su.org.au/api/v4/group/92/-/packages/composer",
                   "https://packagist.org"
                 ],
                 "sourceUrl": "https://github.com/bjeavons/zxcvbn-php",
                 "versioning": "composer",
                 "warnings": [],
                 "updates": [
                   {
                     "bucket": "non-major",
                     "newVersion": "1.4.1",
                     "newValue": "1.4.1",
                     "releaseTimestamp": "2024-11-21T22:10:41.000Z",
                     "newVersionAgeInDays": 60,
                     "newMajor": 1,
                     "newMinor": 4,
                     "newPatch": 1,
                     "updateType": "minor",
                     "branchName": "renovate/bjeavons-zxcvbn-php-1.x"
                   }
                 ]
               }
             ],
             "extractedConstraints": {"php": ">=8.2"},
             "lockFiles": ["composer.lock"],
             "managerData": {"composerJsonType": "project"},
             "packageFile": "composer.json"
           }
         ]
       }
DEBUG: detectSemanticCommits() (repository=test/renovate-composer-filtering)
DEBUG: semanticCommits: returning "disabled" from cache (repository=test/renovate-composer-filtering)
DEBUG: processRepo() (repository=test/renovate-composer-filtering)
DEBUG: Processing 1 branch: renovate/bjeavons-zxcvbn-php-1.x (repository=test/renovate-composer-filtering)
DEBUG: Calculating hourly PRs remaining (repository=test/renovate-composer-filtering)
DEBUG: currentHourStart=2025-01-21T01:00:00.000+00:00 (repository=test/renovate-composer-filtering)
DEBUG: PR hourly limit remaining: 2 (repository=test/renovate-composer-filtering)
DEBUG: Calculating prConcurrentLimit (10) (repository=test/renovate-composer-filtering)
DEBUG: getBranchPr(renovate/bjeavons-zxcvbn-php-1.x) (repository=test/renovate-composer-filtering)
DEBUG: findPr(renovate/bjeavons-zxcvbn-php-1.x, undefined, open) (repository=test/renovate-composer-filtering)
DEBUG: getPr(1) (repository=test/renovate-composer-filtering)
DEBUG: getMR(1) (repository=test/renovate-composer-filtering)
DEBUG: GET https://version-control.it.su.org.au/api/v4/group/92/-/packages/composer/p2/bjeavons/zxcvbn-php~dev.json = (code=ERR_NON_2XX_3XX_RESPONSE, statusCode=404 retryCount=0, duration=191) (repository=test/renovate-composer-filtering)
DEBUG: 1 PRs are currently open (repository=test/renovate-composer-filtering)
DEBUG: PR concurrent limit remaining: 9 (repository=test/renovate-composer-filtering)
DEBUG: Calculated maximum PRs remaining this run: 2 (repository=test/renovate-composer-filtering)
DEBUG: PullRequests limit = 2 (repository=test/renovate-composer-filtering)
DEBUG: Calculating hourly PRs remaining (repository=test/renovate-composer-filtering)
DEBUG: currentHourStart=2025-01-21T01:00:00.000+00:00 (repository=test/renovate-composer-filtering)
DEBUG: PR hourly limit remaining: 2 (repository=test/renovate-composer-filtering)
DEBUG: Calculating branchConcurrentLimit (3) (repository=test/renovate-composer-filtering)
DEBUG: 1 already existing branches found: renovate/bjeavons-zxcvbn-php-1.x (repository=test/renovate-composer-filtering)
DEBUG: Branch concurrent limit remaining: 2 (repository=test/renovate-composer-filtering)
DEBUG: Calculated maximum branches remaining this run: 2 (repository=test/renovate-composer-filtering)
DEBUG: Branches limit = 2 (repository=test/renovate-composer-filtering)
DEBUG: syncBranchState() (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
DEBUG: branch.isUpToDate(): using cached result "true" (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
DEBUG: getBranchPr(renovate/bjeavons-zxcvbn-php-1.x) (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
DEBUG: findPr(renovate/bjeavons-zxcvbn-php-1.x, undefined, open) (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
DEBUG: getPr(1) (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
DEBUG: getMR(1) (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
DEBUG: branchExists=true (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
DEBUG: dependencyDashboardCheck=rebase (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
DEBUG: PR rebase requested=false (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
DEBUG: Checking if PR has been edited (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
DEBUG: branch.isModified(): using cached result "false" (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
DEBUG: Found existing branch PR (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
DEBUG: Checking schedule(schedule=at any time, tz=null, now=2025-01-21T01:34:10.949Z) (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
DEBUG: No schedule defined (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
DEBUG: User has requested rebase (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
DEBUG: Using reuseExistingBranch: false (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
DEBUG: Setting current branch to main (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
DEBUG: Initializing git repository into /builds/it-internal/renovate-runner/renovate/repos/gitlab/test/renovate-composer-filtering (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
DEBUG: Performing blobless clone (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
DEBUG: git clone completed (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
       "durationMs": 1539
DEBUG: latest repository commit (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
       "latestCommit": {
         "hash": "e8476e43e955065227c31ffcbc621200dd9b8a0f",
         "date": "2025-01-21T09:28:05+08:00",
         "message": "Downgrade for testing",
         "refs": "HEAD -> main, origin/main, origin/HEAD",
         "body": "",
         "author_name": "Tim White",
         "author_email": "tim.white@su.org.au"
       }
DEBUG: latest commit (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
       "branchName": "main",
       "latestCommitDate": "2025-01-21T09:28:05+08:00"
DEBUG: manager.getUpdatedPackageFiles() reuseExistingBranch=false (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
DEBUG: Starting search at index 681 (repository=test/renovate-composer-filtering, packageFile=composer.json, branch=renovate/bjeavons-zxcvbn-php-1.x)
       "depName": "bjeavons/zxcvbn-php"
DEBUG: Found match at index 681 (repository=test/renovate-composer-filtering, packageFile=composer.json, branch=renovate/bjeavons-zxcvbn-php-1.x)
       "depName": "bjeavons/zxcvbn-php"
DEBUG: Contents updated (repository=test/renovate-composer-filtering, packageFile=composer.json, branch=renovate/bjeavons-zxcvbn-php-1.x)
       "depName": "bjeavons/zxcvbn-php"
DEBUG: updateArtifacts for updatedPackageFiles (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
DEBUG: composer.updateArtifacts(composer.json) (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
DEBUG: Using php constraint from config (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
DEBUG: Using GitHub Personal Access Token (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
DEBUG: Setting CONTAINERBASE_CACHE_DIR to /cache/renovatebotcache/containerbase (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
DEBUG: Using containerbase dynamic installs (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
DEBUG: Resolved stable matching version (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
       "toolName": "php",
       "constraint": "<=8.2.0",
       "resolvedVersion": "8.2.0"
DEBUG: Resolved stable matching version (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
       "toolName": "composer",
       "constraint": "^2.6",
       "resolvedVersion": "2.8.4"
DEBUG: Executing command (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
       "command": "install-tool php 8.2.0"
DEBUG: exec completed (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
       "durationMs": 4273,
       "stdout": "[01:34:13.091] INFO (134): Installing tool php@8.2.0...\nPHP 8.2.0 (cli) (built: Dec  9 2022 15:53:08) (NTS)\nCopyright (c) The PHP Group\nZend Engine v4.2.0, Copyright (c) Zend Technologies\n[01:34:16.426] INFO (134): Install tool php succeeded in 3.3s.\n",
       "stderr": ""
DEBUG: Executing command (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
       "command": "install-tool composer 2.8.4"
DEBUG: exec completed (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
       "durationMs": 711,
       "stdout": "[01:34:17.356] INFO (149): Installing tool composer@2.8.4...\nComposer version 2.8.4 2024-12-11 11:57:47\nPHP version 8.2.0 (/opt/containerbase/tools/php/8.2.0/bin/php)\nRun the \"diagnose\" command to get more detailed diagnostics output.\n[01:34:17.705] INFO (149): Install tool composer succeeded in 353ms.\n",
       "stderr": ""
DEBUG: Executing command (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
       "command": "composer update bjeavons/zxcvbn-php:1.4.1 --with-dependencies --ignore-platform-req='ext-*' --ignore-platform-req='lib-*' --no-ansi --no-interaction --no-scripts --no-autoloader --no-plugins"
DEBUG: exec completed (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
       "durationMs": 1195,
       "stdout": "",
       "stderr": "Warning: You should avoid overwriting already defined auth settings for version-control.it.su.org.au.\nLoading composer repositories with package information\nUpdating dependencies\nLock file operations: 0 installs, 1 update, 0 removals\n  - Upgrading bjeavons/zxcvbn-php (1.3.1 => 1.4.1)\nWriting lock file\nInstalling dependencies from lock file (including require-dev)\nPackage operations: 2 installs, 0 updates, 0 removals\n  - Installing symfony/polyfill-mbstring (v1.31.0): Extracting archive\n  - Installing bjeavons/zxcvbn-php (1.4.1): Extracting archive\n1 package you are using is looking for funding.\nUse the `composer fund` command to find out more!\nNo security vulnerability advisories found.\n"
DEBUG: Returning updated composer.lock (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
DEBUG: Updated 1 package files (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
DEBUG: Updated 1 lock files (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
       "updatedArtifacts": ["composer.lock"]
DEBUG: Ensuring comment "⚠️ Artifact update problem" in #1 is removed (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
DEBUG: Getting comments for #1 (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
DEBUG: Found 1 comments (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
DEBUG: Ensuring comment "ℹ Artifact update notice" in #1 is removed (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
DEBUG: Getting comments for #1 (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
DEBUG: Found 1 comments (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
DEBUG: isBranchConflicted(main, renovate/bjeavons-zxcvbn-php-1.x) (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
DEBUG: branch.isConflicted(): using cached result "false" (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
DEBUG: 2 file(s) to commit (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
DEBUG: Preparing files for committing to branch renovate/bjeavons-zxcvbn-php-1.x (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
DEBUG: Setting git author name: Renovate Bot (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
DEBUG: Setting git author email: itdepartment+renovate@su.org.au (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
DEBUG: git commit (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
       "deletedFiles": [],
       "ignoredFiles": [],
       "result": {
         "author": null,
         "branch": "renovate/bjeavons-zxcvbn-php-1.x",
         "commit": "2dd48e8c586f611e3bb1a58acddbb0d79d04bdcf",
         "root": false,
         "summary": {"changes": 2, "insertions": 9, "deletions": 8}
       }
DEBUG: Pushing refSpec renovate/bjeavons-zxcvbn-php-1.x:renovate/bjeavons-zxcvbn-php-1.x (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
DEBUG: git push (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
       "result": {
         "pushed": [],
         "ref": {"local": "refs/remotes/origin/renovate/bjeavons-zxcvbn-php-1.x"},
         "remoteMessages": {
           "all": [
             "View merge request for renovate/bjeavons-zxcvbn-php-1.x:",
             "https://version-control.it.su.org.au/test/renovate-composer-filtering/-/merge_requests/1"
           ]
         }
       }
DEBUG: Setting current branch to main (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
DEBUG: latest commit (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
       "branchName": "main",
       "latestCommitDate": "2025-01-21T09:28:05+08:00"
 INFO: Branch updated (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
       "commitSha": "2dd48e8c586f611e3bb1a58acddbb0d79d04bdcf"
DEBUG: Ensuring PR (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
DEBUG: There are 0 errors and 0 warnings (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
DEBUG: getBranchPr(renovate/bjeavons-zxcvbn-php-1.x) (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
DEBUG: findPr(renovate/bjeavons-zxcvbn-php-1.x, undefined, open) (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
DEBUG: getPr(1) (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
DEBUG: getMR(1) (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
DEBUG: Found existing PR (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
DEBUG: PR fingerprints mismatch, processing PR (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
DEBUG: Fetching changelog: https://github.com/bjeavons/zxcvbn-php (1.3.1 -> 1.4.1) (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
DEBUG: Processing existing PR (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
DEBUG: setPrCache() (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
DEBUG: Pull Request #1 does not need updating (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
DEBUG: PR is not configured for automerge (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
DEBUG: setBranchCommit() (repository=test/renovate-composer-filtering, branch=renovate/bjeavons-zxcvbn-php-1.x)
DEBUG: getBranchPr(renovate/bjeavons-zxcvbn-php-1.x) (repository=test/renovate-composer-filtering)
DEBUG: findPr(renovate/bjeavons-zxcvbn-php-1.x, undefined, open) (repository=test/renovate-composer-filtering)
DEBUG: getPr(1) (repository=test/renovate-composer-filtering)
DEBUG: getMR(1) (repository=test/renovate-composer-filtering)
DEBUG: Config does not need migration (repository=test/renovate-composer-filtering)
DEBUG: ensureDependencyDashboard() (repository=test/renovate-composer-filtering)
DEBUG: Ensuring Dependency Dashboard (repository=test/renovate-composer-filtering)
DEBUG: Checking packageFiles for deprecated packages (repository=test/renovate-composer-filtering)
DEBUG: ensureIssue() (repository=test/renovate-composer-filtering)
DEBUG: Updating issue (repository=test/renovate-composer-filtering)
DEBUG: validateReconfigureBranch() (repository=test/renovate-composer-filtering)
DEBUG: No reconfigure branch found (repository=test/renovate-composer-filtering)
DEBUG: Removing any stale branches (repository=test/renovate-composer-filtering)
DEBUG: config.repoIsOnboarded=true (repository=test/renovate-composer-filtering)
DEBUG: Branch lists (repository=test/renovate-composer-filtering)
       "branchList": ["renovate/bjeavons-zxcvbn-php-1.x"],
       "renovateBranches": ["renovate/bjeavons-zxcvbn-php-1.x"]
DEBUG: remainingBranches= (repository=test/renovate-composer-filtering)
DEBUG: No branches to clean up (repository=test/renovate-composer-filtering)
DEBUG: ensureIssueClosing() (repository=test/renovate-composer-filtering)
DEBUG: ensureIssueClosing() (repository=test/renovate-composer-filtering)
DEBUG: PackageFiles.clear() - Package files deleted (repository=test/renovate-composer-filtering)
DEBUG: Branch summary (repository=test/renovate-composer-filtering)
       "cacheModified": true,
       "baseBranches": [{"branchName": "main", "sha": "e8476e43e955065227c31ffcbc621200dd9b8a0f"}],
       "branches": [
         {
           "automerge": false,
           "baseBranch": "main",
           "baseBranchSha": "e8476e43e955065227c31ffcbc621200dd9b8a0f",
           "branchName": "renovate/bjeavons-zxcvbn-php-1.x",
           "branchSha": "2dd48e8c586f611e3bb1a58acddbb0d79d04bdcf",
           "isModified": false,
           "isPristine": true
         }
       ],
       "defaultBranch": "main",
       "inactiveBranches": []
DEBUG: branches info extended (repository=test/renovate-composer-filtering)
       "branchesInformation": [
         {
           "branchName": "renovate/bjeavons-zxcvbn-php-1.x",
           "prNo": 1,
           "prTitle": "Update dependency bjeavons/zxcvbn-php to v1.4.1",
           "result": "done",
           "upgrades": [
             {
               "datasource": "packagist",
               "depName": "bjeavons/zxcvbn-php",
               "displayPending": "",
               "fixedVersion": "1.3.1",
               "currentVersion": "1.3.1",
               "currentValue": "1.3.1",
               "newValue": "1.4.1",
               "newVersion": "1.4.1",
               "packageFile": "composer.json",
               "updateType": "minor",
               "packageName": "bjeavons/zxcvbn-php"
             }
           ]
         }
       ]
DEBUG: Renovate repository PR statistics (repository=test/renovate-composer-filtering)
       "stats": {"total": 1, "open": 1, "closed": 0, "merged": 0}
DEBUG: Repository result: done, status: onboarded, enabled: true, onboarded: true (repository=test/renovate-composer-filtering)
DEBUG: Repository timing splits (milliseconds) (repository=test/renovate-composer-filtering)
       "splits": {"init": 1261, "extract": 341, "lookup": 190, "onboarding": 1, "update": 10107},
       "total": 13479
DEBUG: Package cache statistics (repository=test/renovate-composer-filtering)
       "get": {"count": 14, "avgMs": 6, "medianMs": 2, "maxMs": 40, "totalMs": 80},
       "set": {"count": 2, "avgMs": 5, "medianMs": 7, "maxMs": 7, "totalMs": 10}
DEBUG: HTTP statistics (repository=test/renovate-composer-filtering)
       "hosts": {
         "version-control.it.su.org.au": {
           "count": 11,
           "reqAvgMs": 262,
           "reqMedianMs": 141,
           "reqMaxMs": 1130,
           "queueAvgMs": 0,
           "queueMedianMs": 0,
           "queueMaxMs": 0
         }
       },
       "requests": 11
DEBUG: HTTP cache statistics (repository=test/renovate-composer-filtering)
DEBUG: Lookup statistics (repository=test/renovate-composer-filtering)
       "github-tags": {"count": 1, "avgMs": 131, "medianMs": 131, "maxMs": 131, "totalMs": 131},
       "packagist": {"count": 1, "avgMs": 164, "medianMs": 164, "maxMs": 164, "totalMs": 164}
 INFO: Repository finished (repository=test/renovate-composer-filtering)
       "cloned": true,
       "durationMs": 13479
```
