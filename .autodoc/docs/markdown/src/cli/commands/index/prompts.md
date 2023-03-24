[View code on GitHub](https://github.com/context-labs/autodoc/blob/master/src/cli/commands/index/prompts.ts)

This code file provides three utility functions that generate prompts for code documentation tasks. These functions are designed to help developers create documentation for a given project, specifically focusing on individual files, questions about the code, and folder summaries.

1. `createCodeFileSummary(filePath, projectName, fileContents)`: This function takes in three parameters - the file path, the project name, and the contents of the file. It returns a formatted string prompt that asks the developer to write a detailed technical explanation of the code in the given file. The prompt specifies that the response should be in markdown format, between 100 and 300 words, and should not mention that the file is part of the project or just list the methods and classes in the file.

   Example usage:
   ```
   const prompt = createCodeFileSummary('src/utils/helper.js', 'MyProject', 'const add = (a, b) => a + b;');
   ```

2. `createCodeQuestions(filePath, projectName, fileContents)`: This function also takes in the file path, project name, and file contents as parameters. It returns a formatted string prompt that asks the developer to come up with three questions that a knowledgeable developer might have about the code and answer them in 1-2 sentences. The output should be in markdown format.

   Example usage:
   ```
   const prompt = createCodeQuestions('src/utils/helper.js', 'MyProject', 'const add = (a, b) => a + b;');
   ```

3. `folderSummaryPrompt(folderPath, projectName, files, folders)`: This function takes in the folder path, project name, an array of `FileSummary` objects, and an array of `FolderSummary` objects. It returns a formatted string prompt that asks the developer to write a technical explanation of the code in the folder and how it might fit into the larger project. The prompt includes a list of files and subfolders in the folder, along with their summaries. The response should be in markdown format and under 400 words.

   Example usage:
   ```
   const prompt = folderSummaryPrompt('src/utils', 'MyProject', fileSummaries, folderSummaries);
   ```

These utility functions can be used in the larger project to generate documentation prompts for various parts of the codebase, helping developers better understand the code and its purpose within the project.
## Questions: 
 1. **Question:** What is the purpose of the `createCodeFileSummary` function?
   **Answer:** The `createCodeFileSummary` function generates a template string that prompts the user to write a detailed technical explanation of the code in a given file, focusing on its high-level purpose and how it may be used in the larger project.

2. **Question:** How does the `createCodeQuestions` function differ from the `createCodeFileSummary` function?
   **Answer:** The `createCodeQuestions` function generates a template string that prompts the user to come up with three questions that a super smart developer might have about the code in a given file and answer each question in 1-2 sentences, while the `createCodeFileSummary` function prompts the user to write a detailed technical explanation of the code.

3. **Question:** What is the purpose of the `folderSummaryPrompt` function and what information does it require?
   **Answer:** The `folderSummaryPrompt` function generates a template string that prompts the user to write a technical explanation of the code in a given folder and how it might fit into the larger project. It requires the folder path, project name, a list of files with their summaries, and a list of subfolders with their summaries.