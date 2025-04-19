# Setup

## 1. Set Environment Variable

Ensure pipenv installs packages in the virtual environment of the current project. This forces the virtual environment to be created inside the project directory (in `.venv`).

```sh
export PIPENV_VENV_IN_PROJECT=1
```

## 2. Set the environment file .env variable with following keys

Modify the value for HF_TOKEN to reflect your Hugging Face token and replace value for PROJECT_PATH to reflect where you have cloned this project

```sh
HF_TOKEN=hf_XXXX
PROJECT_PATH=D:\gitprojects
OPEN_AI_TOKEN=sk-XXXXXXX


```

## 3. Create Conda Environment

Create a Conda environment with Python 3.11.11

```sh
conda create --prefix ./.venv python=3.11.11
```

## 4. Install Packages

Install the required packages using pipenv.

```sh
pipenv install
```

# Running the Apps

## OhSheet!!!ItsSpark

### 1. Navigate to below Jupyter Notebook
```
llm_apps\oh_sheet_its_spark\app.ipynb
```
### 2. Select Jupyter Kernel that resides inside the script directory of virtual environment

![1736345956285](image/Readme/1736345956285.png)

### 3. Click Run All

![1736346134406](image/Readme/1736346134406.png)

### 4. Gradio App Opens in the browser

Gradio app will then open in the browser . Use upload button to select spreadsheet you want to convert to pyspark & the app immediately generates the pyspark equivalent code.If you want some more ad-hoc changes , use the message textarea to describe your specific changes

![1736346248968](image/Readme/1736346248968.png)

### 5. Changing the Model Used

#### Switching Models to use a different free Inference Client thats Warm

Simply change value of the variable inf_mdl_nm currently to "Qwen/Qwen2.5-Coder-32B-Instruct"

```python
inf_mdl_nm = "Qwen/Qwen2.5-Coder-32B-Instruct"
```

#### Switching To your own private model

If you want to switch to your own privately deployed or locally quantised model simply replace the below 2 method invocations with your own method which invokes the LLM passing the message variables **initial_msg** and **msg_history** to the 2 different calls

```python
cd_resp = generate_responses_from_inf(hf_token, initial_msg, inf_mdl_nm, 5000)
```

```python
bot_response = generate_responses_from_inf(hf_token, msg_history, inf_mdl_nm, 5000)
```

### 6. Using Test File for Upload

You can use the below file path in the project to test uploads:
```
datasets\test_datasets\SalesData1.xlsx
```



# 𝗢𝗵 𝗦𝗵𝗲𝗲𝘁! 𝗜𝘁’𝘀 𝗦𝗽𝗮𝗿𝗸! 😅 (See Video below!!!!)
Nope, I didn’t cuss—read that again! That’s the title of my new 𝗟𝗟𝗠/𝗚𝗲𝗻𝗔𝗜 app for data engineers, served with ❤️ using Gradio.

Let’s face it: in the Data Engineering world, 𝘀𝘆𝗻𝗲𝗿𝗴𝘆 𝗯𝗲𝘁𝘄𝗲𝗲𝗻 𝗕𝘂𝘀𝗶𝗻𝗲𝘀𝘀 𝗔𝗻𝗮𝗹𝘆𝘀𝘁𝘀 𝗮𝗻𝗱 𝗗𝗮𝘁𝗮 𝗘𝗻𝗴𝗶𝗻𝗲𝗲𝗿𝘀 often looks like… spreadsheets. Lots of them. They come packed with complex business logic, formulas referencing multiple sheets, and dependencies that make your head spin. As Data Engineers, we end up scrambling through formulas trying to figure out which column derives what, with inputs scattered across sheets like confetti at a party. 🎉

Sure, ChatGPT can help… but:

• The free plan limits you to a handful of spreadsheet uploads.
• Formula extraction isn’t always accurate (yet).
• Feeding sensitive company data to a private model? Risky. 🚨

𝗘𝗻𝘁𝗲𝗿 “𝗢𝗵 𝗦𝗵𝗲𝗲𝘁! 𝗜𝘁’𝘀 𝗦𝗽𝗮𝗿𝗸!” 🚀
This app takes your spreadsheet upload, extracts 𝗳𝗼𝗿𝗺𝘂𝗹𝗮𝘀 𝗮𝗰𝗿𝗼𝘀𝘀 𝗮𝗹𝗹 𝘀𝗵𝗲𝗲𝘁𝘀, figures out the 𝗱𝗲𝗽𝗲𝗻𝗱𝗲𝗻𝗰𝗶𝗲𝘀, and generates 𝗲𝗾𝘂𝗶𝘃𝗮𝗹𝗲𝗻𝘁 𝗣𝘆𝗦𝗽𝗮𝗿𝗸 𝗰𝗼𝗱𝗲. From there, you can continue asking for tweaks or updates.

Currently, it’s powered by 𝗤𝘄𝗲𝗻/𝗤𝘄𝗲𝗻𝟮.𝟱-𝗖𝗼𝗱𝗲𝗿-𝟯𝟮𝗕-𝗜𝗻𝘀𝘁𝗿𝘂𝗰𝘁, hosted on Hugging Face’s free Warm Inference endpoint. But here’s the kicker: you can swap it with 𝗮𝗻𝘆 𝘄𝗮𝗿𝗺 𝗺𝗼𝗱𝗲𝗹 or 𝘆𝗼𝘂𝗿 𝗽𝗿𝗶𝘃𝗮𝘁𝗲𝗹𝘆 𝘀𝗲𝗿𝘃𝗲𝗱 𝗟𝗟𝗠 by changing just two lines of code. (Pro tip: Check out the last 20 seconds of the demo video for how-to!)

𝗕𝗲𝗵𝗶𝗻𝗱 𝘁𝗵𝗲 𝗦𝗰𝗲𝗻𝗲𝘀 🛠️
Since 𝗼𝗽𝗲𝗻𝗽𝘆𝘅𝗹 has its limitations with formula extraction, the app uses the 𝘅𝗹𝘄𝗶𝗻𝗴𝘀 library, which connects natively to Excel. That means it’s deployable only on a server with an active 𝗘𝘅𝗰𝗲𝗹 𝗶𝗻𝘀𝘁𝗮𝗹𝗹𝗮𝘁𝗶𝗼𝗻.

If you’re a Data Engineer dealing with spreadsheets or a BA tired of translating formulas, this is for you! Let’s streamline that workflow and focus on what matters.
Video Link: 

https://github.com/user-attachments/assets/cd77570c-bb08-46bb-acd6-fa288b179c50


Repo link : https://lnkd.in/egG62Uit
