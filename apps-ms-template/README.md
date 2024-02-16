# Commands for each project

1. Populate `node_modules/`

       npm install

1. ...

1. Run `src/app.js`

       npm run dev:teamsfx


# Projects

|tamplate id                   |templates directory|
|------------------------------|-------------------|
|bot                           |default-bot        |
|ai-bot                        |
|notification                  |
|command-bot                   |
|workflow-bot                  |
|tab-non-sso                   |non-sso-tab        |
|sso-launch-page               |
|dashboard-tab                 |
|tab-spfx                      |
|search-app                    |
|collect-form-message-extension|
|search-message-extension      |
|link-unfurling                |

1. `tamplate id` as in `teamsapp list templates`
2. `templates directory` as in https://github.com/OfficeDev/TeamsFx/tree/dev/templates/js/


## non-sso-tab-js-01

1. Create a project

       npm run -- teamsapp new --app-name non-sso-tab-js-01 \
               --capability tab-non-sso \
               --folder apps-ms-template/ \
               --interactive false

1. The files are generated from https://github.com/OfficeDev/TeamsFx/tree/dev/templates/js/non-sso-tab/
    1. [e7b6eb4](https://github.com/OfficeDev/TeamsFx/commit/e7b6eb4aae11e12c5e0b7c007c18f7e0700f13b9) (2023-11-16) has not been applied
    1. [149fcc0](https://github.com/OfficeDev/TeamsFx/commit/149fcc03572b6f7b244f3b1f9ba92c4e66df3e00) (2023-11-09) has been applied
    1. It seems the template at `teamsapp-cli-3.0.0-alpha.ec50e3de8.0` (2023-11-13) is used

## non-sso-tab-ts-01

1. Create a project

       npm run -- teamsapp new --app-name non-sso-tab-js-01 \
               --capability tab-non-sso \
               --programming-language typescript \
               --folder apps-ms-template/ \
               --interactive false

## bot-file-upload-01

1. `Debug` with Teams Toolkit 5.4.1 on Visual Studio Code
    1. A dialog says `The Teams Toolkit requires an Azure account and subscription to deploy the Azure resources for your project. You will not be charged without further confirmation`
        1. `Sign in` with a account with [Microsoft 365 Developer Program](https://developer.microsoft.com/en-us/microsoft-365/profile) doesn't fix the situation
        1. `Sign in` with a tenant user results in
            1. `Successfully signed in to Azure account.` but
            1. `[login.UserError]: Failed to find a subscription.`
            1. Can be signed off by clicking the user name at the bottom bar
                1. `Sign in to Azure` in the navigation does not work until signed off
        1. This dialog doesn't appear when `Sign in to Azure` is already done
    1. `subscription is not selected, try to select`
        1. `Select Subscriptions...` by clicking the user name at the bottom bar
    1. `Select a resource group`
        1. Select one and `Provision`
        1. This appears after the generated files in the project directory are deleted.


## Generated but uncommitted files

They are the same for every project.

## `.localConfigs`

    # A gitignored place holder file for local runtime configurations
    BROWSER=none
    HTTPS=true
    PORT=
    SSL_CRT_FILE=
    SSL_KEY_FILE=

## `env/.env.local`

    # This file includes environment variables that can be committed to git. It's gitignored by default because it represents your local development environment.

    # Built-in environment variables
    TEAMSFX_ENV=local
    APP_NAME_SUFFIX=local


    # Generated during provision, you can also add your own variables.
    TAB_DOMAIN=
    TAB_ENDPOINT=
    TEAMS_APP_ID=
    TEAMS_APP_PACKAGE_PATH=

    # Generated during deploy, you can also add your own variables.
    SSL_CRT_FILE=
    SSL_KEY_FILE=


# Remarks

1. `projectId` line in `teamsapp.yml`
    1. `apps-ms-template`: `teamsapp new` generates a new line
    2. `apps-ms-sample`: a new line is appended on the first run

