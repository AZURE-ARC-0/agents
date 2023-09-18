## 😄 Getting Started with Fun


### 1.Install the package
- [x] Option 1.  Build from source

    ```bash
    git clone https://github.com/aiwaves-cn/agents.git
    cd agents
    pip install -e . 
    ```

- [x] Option 2.  Install via PyPI

    ```bash
    pip install ai-agents
    ```
 ### 2.Single Agent🤖️   
#### Set  config firstly(examples/Single_Agent/{target_agent}/config.json)
```
{  // e.g. for shopping assistant（due to change the search engine，it maybe not work now）
    MIN_CATEGORY_SIM  =  "0.7"  ##Threshold for category matching
    TOY_INFO_PATH  = "[\"your_path1\",\"your_path2_\"......]" #Path to the product database
    FETSIZE  =  "5" #Number of recommended products at a time
    SHOPPING_SEARCH = "Your url"  # Your search engine
    
    #for all agents
    API_KEY  =  #Your API KEY
    PROXY  =  #Your proxy
    MAX_CHAT_HISTORY  =  "8" #Longest History
    User_Names = "[\"{user_name}\"]" # the name of agents which you want to play  
}
```


Note that if you want to use `WebSearchComponent`, you also need set the config!

```
 "WebSearchComponent": {
                        "engine_name": "bing",
                        "api": {
                            "google": {
                                "cse_id": "Your cse_id",
                                "api_key": "Your api_key"
                            },
                            "bing": "Your bing key"
                        }
                    }
```
- [x] Option 1.  Run on your terminal

    ```bash
    cd examples
    python run.py --agent Single_Agent/{target_agent}/config.json
    ```

- [x] Option 2. Run on gradio
	
    ```bash
   cd examples
   # `run_gradio.py` depends on `gradio_backend.py`.
   python Single_Agent/run_gradio.py --agent Single_Agent/{target_agent}/config.json
   ```
- [ ] Option 3. Run on fast api
    ```bash
   cd examples
   python run_backend.py --agent Single_Agent/{target_agent}/config.json
   ```


 ### 2.Muti Agent🤖️🤖️   
- [x] Option 1.  Run on your terminal
      
	Modify the config.json

	For example, if you want to play the agent named "Mike" and "Mary"(Support all Agent)
	```
	{ 
	    #for all agents
	    API_KEY  =  #Your API KEY
	    PROXY  =  #Your proxy
	    MAX_CHAT_HISTORY  =  "8" #Longest History
	    User_Names = "[\"Mike\",\"Mary\"]" # the name of agents which you want to play  
	}
	```

    ```bash
    cd examples
    python run.py --agent Muti_Agent/{target_agent}/config.json
    ```

- [x] Option 2. Run on gradio
	
    ```bash
   cd examples/Muti_Agent/{target_agent}
   # `run_gradio.py` depends on `gradio_backend.py`.
   python run_gradio.py
   ```
   Choose the agent you want to perform in the gradio UI.
- [ ] Option 3. Run on fast api
    ```bash
   cd examples
   python run_backend.py --agent Muti_Agent/{target_agent}/config.json
   ```

 ### 3.Start with your own Agent🤖️🤖️🤖️  
 #### 1.Write your config.json according to [template.py](https://github.com/aiwaves-cn/agents/blob/master/src/agents/template.py)(more details refer to the [doc](https://ai-waves.feishu.cn/wiki/NIjrw8FR7inGTMkfS5yc5wcvnlg))
 
 #### 2.Run your config.json 

- [x] Option 1.  Run on your terminal

    ```bash
    cd examples
    python run.py --agent config.json
    ```


- [x] Option 2. Run on gradio
	
    ```bash
   cd examples
   # `run_gradio.py` depends on `gradio_backend.py`.
   python run_gradio.py --agent your_config.json
   ```
    
- [ ] Option 3. Run on fast api
    ```bash
   cd examples
   python run_backend.py --agent config.json
   ```




### 🤖️ The Agent Hub

We provide an **AgentHub**, where you can search for interesting Agents shared by us or other developers, try them out or use them as the starting point to customize your own agent. We encourage you to share your customized agents to help others build their own agents more easily! You can share your customized agents by submitting PRs that adds configs and customized codes [here](https://github.com/aiwaves-cn/agents/tree/master/examples/Community_Agent). You can also send us your own config files and codes for customized agents by [email](mailto:contact@aiwaves.cn), and we will share your examples and acknowledge your contribution in future updates!

A WebUI for automatically uploading of your customized agents will be available soon!
 
