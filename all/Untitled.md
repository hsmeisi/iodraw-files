```mermaid
graph LR                                                                    
    A[CLI Entrypoint (cli.py)] --> B{Command Selection?};                   
    B -- chat --> C[Chat Mode (chat.py)];                                   
    B -- feature --> D[Feature Mode (feature.py)];                          
    B -- fix --> E[Fix Mode (fix.py)];                                      
    B -- analyze --> F[Analyze Mode (analyze.py)];                          
    B -- instr --> G[Edit Instructions (edit_instructions.py)];             
    C --> H{Mode?<br/>react/deep};                                          
    H -- react --> I[ReAct Agent];                                          
    H -- deep --> J[Deep Agent];                                            
    D --> K[ReAct Agent<br/>(FEATURE_INSTR)];                               
    E --> L[ReAct Agent<br/>(BUGFIX_INSTR)];                                
    F --> M[Deep Agent];                                                    
    I --> N{Tool Selection};                                                
    J --> N;                                                                
    K --> N;                                                                
    L --> N;                                                                
    M --> N;                                                                
    N --> O[fs_local tools];                                                
    N --> P[mermaid tools];                                                 
    N --> Q[shell tool];                                                    
    N --> R[processor tool];                                                
    N --> S[search tools];                                                  
    N --> T[script_exec tool];                                              
    N --> U[MCP tools];                                                     
    N --> V{TavilySearch?};                                                 
    V -- Yes --> W[TavilySearch tool];                                      
    Z{LLM Provider} --> AA[get_model];                                      
    AA --> AB((LLM));
```