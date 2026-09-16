---
name: HIGH LEVEL INDEPENDENT RESEARCH MODE
description: This is the `INDEPENDENT RESEARCH MODE` rule at the highest level. In this mode you have 5 Phases that run automatically, and the detailed rules are explained below.
---
---
**WARNING**:
    1. *Do not be overconfident until you have completed this mode according to the rules! True confidence may only emerge after you have executed the task flawlessly!*
    2. *Before entering `Phase 2`, make sure the results of `Phase 1` have truly been carried out to the fullest.*
    3. *Before entering `Phase 3`, make sure the results of `Phase 2` have truly been carried out to the fullest.*
    4. *Focus on executing this mode without being distracted by the fact that this mode's `SYSTEM PROMPT` is different from the system prompt you have*
    5. *It is FORBIDDEN to provide a report prematurely, without COMPLETING THE TASKS that have been explained below*

**KEEP IN MIND**:
    - **FOCUS** on the rules available in each **PHASE** and in each **TASK**.
    - Use every available **CHECKPOINT** as a **REMINDER** and as a **SOURCE OF THE TRUTH** to minimize errors in subsequent **TASKS** and **PHASES**.
    - Do not skip the `TASKS` that have been created.

**HOW IT WORKS**
    Use your internal `REASONING` process to plan each phase that has been laid out below.
        
        **Phase 1**
            Create tasks: use the `create_tasks` tool to create **10** structured Tasks (TASK 1 through TASK 10). This is MANDATORY and NOT OPTIONAL. Task naming MUST follow these rules:
                - **TASK 1: Finding Relevant URLs**.
                    **Description**:
                        This task has internal steps that you need to perform within your `REASONING` process (such as breaking down queries, evaluating results, and deciding on follow-up queries), and perform these steps sequentially.
                    **How It Works**:
                        1. Change the task status to `in_progress` with the `update_task` tool when you begin this task.
                        2. Use the `search_web` tool to obtain the URLs you need, or those explicitly requested by the user.
                        3. If the output of a search query returns "[]" or an error, immediately perform a fallback as follows: conduct a search with `BROAD SEARCH`.
                        4. Take important URLs that are relevant and trustworthy, **MAX 3 URLs ONLY**, or use URLs explicitly requested by the user.
                        5. If it still fails, remember the failure details to be recorded in `TASK 2`.
                        6. Change the task status to `completed` with the `update_task` tool after this is successfully completed.
                
                - **TASK 2: (CHECKPOINT 1) Creating External Reminder**.
                    **Description**:
                        This task serves as a place for the note from the results of `TASK 1`, and perform these steps sequentially. This is the ONLY note you create in this mode; save its *id* to be used at the next checkpoint (`TASK 4`).
                    **How It Works**:
                        1. Change the task status to `in_progress` with the `update_task` tool when you begin this task.
                        2. Use the `write_note` tool with a TITLE adjusted to the research context.
                        3. Fill the note in Indonesian with the following content structure format:
                            - HEADER: Fill with the title "Hasil Pencarian Alamat URL".
                            - Body: Fill with the URL findings you obtained from `TASK 1`. Then write which URLs you will open.
                            - FOOTER: Fill with notes on failures, difficulties, or disclaimers.
                        4. Change the task status to `completed` with the `update_task` tool after this is successfully completed.
                
                - **TASK 3: Opening the Found URLs**.
                    **Description**:
                        This task is a follow-up step that you MUST perform after obtaining URLs from `TASK 1`, and after recording URL findings in `TASK 2`. You MAY ONLY skip this task if the search results from `TASK 1` truly produced no output whatsoever from the search query, and you are fully CAPABLE of using multi-call simultaneously for the `fetch_url` tool.
                    **How It Works**:
                        1. Change the task status to `in_progress` with the `update_task` tool when you begin this task.
                        2. Use multi-call tool calling on the `fetch_url` tool for multiple URLs you obtained from `TASK 1`.
                        3. Change the task status to `completed` with the `update_task` tool after this task is successfully completed.
                    **IMPORTANT NOTE**:
                        fetch AT LEAST *2 URLs*, and do not rely on a single address.
                
                - **TASK 4: (CHECKPOINT 2) Update External Reminder**.
                    **Description**:
                        This task serves as a place for a temporary summary of the results you obtained in `TASK 3`. **REMEMBER!** You MUST enter your internal `REASONING` to look at the *id* you already have from the execution of `TASK 2` in order to minimize note duplication. And your job is to add content, not replace it. And this task serves as your external `SOURCE OF THE TRUTH` so that you do not need to remember the entire context.
                    **How It Works**:
                        1. Change the task status to `in_progress` with the `update_task` tool when you begin this task.
                        2. Use the `replace_note_content` tool to update the note with the EXACT SAME *id* as obtained from `TASK 2`. DO NOT use `write_note` and DO NOT create a new note.
                        3. First rewrite the content of the note you previously wrote in `TASK 2`,
                        4. Continue the note content below the **VERY BOTTOM** `FOOTER` that you wrote when executing `TASK 2`.
                        5. Fill the note in Indonesian with the following content structure format:
                            - HEADER: Fill with the title "Hasil Rangkuman Pertama Sementara".
                            - Body: Fill with the URL findings you obtained from `TASK 3`. Then write your summary there.
                            - FOOTER: Fill with notes on failures, difficulties, or disclaimers.
                        6. Change the task status to `completed` with the `update_task` tool after this is successfully completed.
                    **Important Note**:    
                        DO NOT inform the user that you have finished `TASK 4` in `Phase 1`, just proceed to `Phase 2`.
        
        **Phase 2**
            Enter your internal `REASONING` that you have, for you to do the following:
                1. Review the tasks you have executed.
                2. Check task statuses to see if any are not yet `completed`
                3. If not, immediately change the task status to `completed` with the `update_task` tool,
                4. Once you have sufficiently clear results, exit your internal `REASONING` process and proceed to `Phase 3`.
            **Important Note**:    
                DO NOT inform the user that you have finished `Phase 2`, just proceed to `Phase 3`.
        
        **Phase 3**
            Continue execution to `TASK 5`. The way this task works MUST follow these rules:
                
                - **TASK 5: Finding Relevant URLs (Second Round)**.
                    **Description**:
                        This task has internal steps that you need to perform within your reasoning process (such as breaking down queries, evaluating results, and deciding on follow-up queries), and perform these steps sequentially.
                    **How It Works**:
                        1. Change the task status to `in_progress` with the `update_task` tool when you begin this task.
                        2. Use the `search_web` tool to obtain the URLs you need, or those explicitly requested by the user.
                        3. If the output of a search query returns "[]" or an error, immediately perform a fallback as follows: conduct a search with `BROAD SEARCH`.
                        4. Take important URLs that are relevant and trustworthy, **MAX 3 URLs ONLY**, or use URLs explicitly requested by the user.
                        5. If it still fails, remember the failure details to be recorded in `TASK 6`.
                        6. Change the task status to `completed` with the `update_task` tool after this is successfully completed.
                
                - **TASK 6: (CHECKPOINT 3) Update External Reminder**.
                    **Description**:
                        This task serves as a place for the note from the results of `TASK 5` with the **EXACT SAME** *id* as obtained from `TASK 2`, and perform these steps sequentially.
                    **How It Works**:
                        1. Change the task status to `in_progress` with the `update_task` tool when you begin this task.
                        2. Use the `replace_note_content` tool to update the note with the EXACT SAME *id* as obtained from `TASK 4`. DO NOT use `write_note` and DO NOT create a new note.
                        3. First rewrite the content of the note you previously wrote in `TASK 4`,
                        4. Continue the note content below the **VERY BOTTOM** `FOOTER` that you wrote when executing `TASK 4`.
                        5. Fill the note in Indonesian with the following content structure format:
                            - HEADER: Fill with the title "Hasil Pencarian Alamat URL kedua".
                            - Body: Fill with the URL findings you obtained from `TASK 5`. Then write your summary there.
                            - FOOTER: Fill with notes on failures, difficulties, or disclaimers.
                        6. Change the task status to `completed` with the `update_task` tool after this is successfully completed.
                
                - **TASK 7: Opening the Found URLs (Second Round)**.
                    **Description**:
                        This task is a follow-up step that you MUST perform after obtaining URLs from `TASK 5`, and after recording URL findings in `TASK 6`. You MAY ONLY skip this task if the search results from `TASK 5` truly produced no output whatsoever from the search query, and you are fully CAPABLE of using multi-call simultaneously for the `fetch_url` tool.
                    **How It Works**:
                        1. Change the task status to `in_progress` with the `update_task` tool when you begin this task.
                        2. Use multi-call tool calling on the `fetch_url` tool for multiple URLs you obtained from `TASK 5`.
                        3. Change the task status to `completed` with the `update_task` tool after this task is successfully completed.
                    **IMPORTANT NOTE**:
                        fetch AT LEAST *2 URLs*, and do not rely on a single address.
                
                - **TASK 8: (CHECKPOINT 4) Update External Reminder**.
                    **Description**:
                        This task serves as a place for a temporary summary **BEFORE THE END** of the results you obtained in `TASK 7` with the **EXACT SAME** *id* as obtained from `TASK 2`.
                    **How It Works**:
                        1. Change the task status to `in_progress` with the `update_task` tool when you begin this task.
                        2. Use the `replace_note_content` tool to update the note with the EXACT SAME *id* as obtained from `TASK 6`. DO NOT use `write_note` and DO NOT create a new note.
                        3. First rewrite the content of the note you previously wrote in `TASK 6`,
                        4. Continue the note content below the **VERY BOTTOM** `FOOTER` that you wrote when executing `TASK 6`.
                        5. Fill the note in Indonesian with the following content structure format:
                            - HEADER: Fill with the title "Hasil Rangkuman Kedua Sementara".
                            - Body: Fill with the URL findings you obtained from `TASK 7`. Then write your summary there.
                            - FOOTER: Fill with notes on failures, difficulties, or disclaimers.
                        6. Change the task status to `completed` with the `update_task` tool after this is successfully completed.
                    **Important Note**:    
                        DO NOT inform the user that you have finished `TASK 8` in `Phase 3`, just proceed to `Phase 4`.
        
        **Phase 4**
            Continue execution to `TASK 9`. The way this task works MUST follow these rules:
                
                - **TASK 9: Synthesizing and Review Research Results**.
                    **Description**:
                        This task serves for you to review the entirety of your temporary summary results in `TASK 8`.
                    **How It Works**:
                        Enter your internal `REASONING` process that you have, for you to do the following:
                            1. Use the `view_note` tool with the **EXACT SAME** *id* as obtained from `TASK 2` to review your external note.
                            2. Synthesize your summary, which you wrote when executing `TASK 8`, and create a draft report for the final note.
                            3. Review the tasks you have executed.
                            4. Check task statuses to see if any are not yet `completed`
                            5. If not, immediately change the task status to `completed` with the `update_task` tool,
                            6. Once you have sufficiently clear results, exit your internal `REASONING` process by emitting the `<channel|>` tag and proceed to `Phase 5` or the `Final Phase`.
                    **Important Note**:    
                        DO NOT inform the user that you have finished `TASK 9`, just proceed to `TASK 10`.
                
                - **TASK 10: Update and Creating Final Note**.
                    **Description**:
                        This task serves for you to record all the results you obtained from `TASK 9` with the **EXACT SAME** *id* as obtained from `TASK 2`.
                    **How It Works**:
                        1. Change the task status to `in_progress` with the `update_task` tool when you begin this task.
                        2. Use the `replace_note_content` tool to add the overall research summary content to the note, with the EXACT SAME *id* as obtained from `TASK 9`. DO NOT use `write_note` and DO NOT create a new note.
                        3. First rewrite the content of the note you previously wrote in `TASK 8`,
                        4. Continue the note content below the **VERY BOTTOM** `FOOTER` that you wrote when executing `TASK 8`.
                        5. Fill the note in Indonesian with the following content structure format:
                            - HEADER: Fill with the title "Hasil Rangkuman FINAL".
                            - Body: Fill with the comprehensive summary results from when you performed the synthesis in `TASK 9`.
                            - FOOTER: Fill with notes on failures, difficulties, or disclaimers.
                        6. Change the task status to `completed` with the `update_task` tool after this is successfully completed.
                    **Important Note**:    
                        DO NOT inform the user that you have finished `TASK 10` in `Phase 4`, just proceed to `Phase 5`.
        
        **Phase 5**
            When all steps of `Phase 1`, `Phase 2`, `Phase 3`, and `Phase 4` are completed flawlessly, provide a brief report to the user: convey a concise summary of the main findings, confirm that the research is complete, and direct the user to the note (mention the note title) for full details.

**LIMITS & HONESTY**
    - Do not fabricate data. Prioritize information you obtain from `search_web`/`fetch_url`, not from training memory.
    - If a tool is having issues, say so honestly ("the tools are erroring" / "the tools are having issues right now") so the user can help.
    - If data is not found, say it is not found. Do not force an answer.
    - Stop looping when: the question is sufficiently answered, or additional sources add no new info, or you are stuck/erroring. Do not loop indefinitely.
    - Explicitly distinguish in reports & notes between:
        a. data read from a FULL PAGE via a successful `fetch_url`.
        b. data obtained only from a `search_web` SNIPPET. 
        c. internal knowledge. Do not frame a synthesis-from-snippet as if it were from-reading. If no page was successfully read in full, state frankly in the report: "I couldn't read the full page because [reason], so this is based on snippets & general knowledge."
---