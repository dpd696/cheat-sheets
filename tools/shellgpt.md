# SHELLGPT

## INSTALL PYTHON AND PIP

- Check if Python is installed
```
python3 --version
```
- If not then install
```
sudo apt install python3
```
- Now install PIP
```
sudo apt install python3-pip
```
- Check PIP Version and Compare Python Versions
```
pip --version
```
- It's Best Practice to install a Python Virtual Environment. This is an isolated environment that prevents conflicts with other libraries
```
sudo apt install python3-venv
```
- A Virtual Environment should have its on Dirctory to keep all files organized. Create the Directory and move to it.
```
mkdir ~/shellgpt
cd shellgpt/
```
- Now Create and Label the Virtual Environment and Move to that Directory
```
python3 -m venv gpt-cli
cd gpt-cli/
```
- Now that the Virtual Environment it Created we need to Activate it to Start it
```
source bin/activate
```
- Confirm you are in the Virtual Environment by the Terminal Prefix (gpt-cli) and Install Shell GPT
```
pip3 install shell-gpt
```

---
### OPEN AI KEY

In order to continue you need to optain an OPEN API KEY. To do this navigate to https://open.ai and create an account.

- Create Environment Varible for OPEN API KEY. Create and Copy API KEY from your account.
```
export OPEN_API_KEY="Paste Open API Key"
```
- Confirm Varible
```
env | grep -i openai
```
- Varibles are Temporarily Stored unless added to INIT File. Open /.bashrc and add OPEN_API_KEY="Paste Open API Key at the end of the Script.
```
nano ~/.bashrc
```
- Alternatively to storing the API Key as an Environmental Varible is to add it to the ShellGPT runtime configuration file.
```
nano ~/.config/shell_gpt/.sgptrc
```

---
## TEST SHELL GPT

```
sgpt "Your question or quote"
```

---
## EXAMPLE

```
sgpt --temperature 0 --code "Python script that prompts the user for an URL, connects to that URL using HTTP, requests the HTML page and saves its contents locally in a file. The filename should start with the URL entered by the user, followed by index.html. Answer with the code only."
```
- You can then redirect it to a script
```
sgpt --temperature 0 --code "Python script that prompts the user for an URL, connects to that URL using HTTP, requests the HTML page and saves its contents locally in a file. The filename should start with the URL entered by the user, followed by index.html. Answer with the code only." > web_scraping.py
```
- Then run the script
```
python3 web_scraping.py
```
- When prompted Enter URL: https://www.website.com

---
## Options

COMMAND | DESCRIPTION
---|---
-s or --shell | answers with a shell command
-e or --execute | executes the command

- Example
```
sgpt -se "update my system"
```