# devspaceai

This project configures Dev Spaces to utilise Continue and an LLM to provide some "vibe" coding experience. This is designed to work with the RH Developer Sandbox version of Dev Spaces (which is free) and atm relies on LLMs served by our internal MaaS server, however most OpenAi or ollama models are compatible by configuring Continue

This repo contains a devfile which can be used to created the workspacxe and install Continue. It includes some example config.yaml file that references some model defintions, in what Continue refers to as "local" models (as opposed to the Cloud based OpenAI, Claude etc)

## Prompt: 
This is suggested prompt for Continue to work on to deliver a streamlit based AI client calling an llm to summarize files.

```
Can you write me some python code based around streamlit that presents a ui to upload files, and then
summarizes the file content using an openai v1 based llm rest api. Need to support file types pdf, txt and json.
I'm using python 3.11.
My llm model is called "granite-3-8b-instruct" available at this REST API <https://>
```

## Terminal:
Because Dev Spaces is container based, using a rhel8 universal developer image (with python 3.11 preinstalled) its hard to install new components without create a `venv`. Here is the terminal code to do that before installing any recommended packages from the chat responses.

```
python --version
python -m venv --upgrade-deps venv
source venv/bin/activate
pip3 install --no-cache-dir <....>
```
