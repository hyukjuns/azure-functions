# Azure Monitor Alert to Slack

## Pre Requisite
1. VSCode
2. [VSCode Python Extension](https://marketplace.visualstudio.com/items?itemName=ms-python.python)
3. [VSCode Azure Functions Extenstion](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-azurefunctions)
4. [VSCode Azurite Extension](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-azurefunctions)
## Configuration Step
1. Function 생성 (In VSCode)
    - Consumption Plan
    - LANG: Python 3.11.2
    - Trigger Type: HTTP Trigger
    - ENV
        - SLACK_BOT_TOKEN 
            - 로컬에서 개발할 경우 local.settings.json에 입력
            - Function App에 배포할 경우 Environments에 입력
        - SLACK_CHANNEL_ID
            - 알람을 받을 슬랙 채널 아이디
    - Auth Level - Funciton
2. Slack Bot 구성
    - Slack API: [**chat.postMessage**](https://api.slack.com/methods/chat.postMessage)
    - Permission
        - Bot Token Scope: [**chat:write**](https://api.slack.com/scopes/chat:write)
    - 알림 받고자 하는 채널에 Bot 추가
3. Azure Monitor - Action Group 구성
    - Action -> Webhook -> Function Trigger URL