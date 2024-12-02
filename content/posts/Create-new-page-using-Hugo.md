---
title: "Create a new page using Hugo Static Site Generator"
date: 2024-11-17T17:31:32+01:00
tags: ['Hugo','SSG', 'Static Site Generator']
featured_image: "/images/500/hugo-2000x500.png"
draft: false
toc: true
show_reading_time: true
omit_header_text: true
summary: "How to guide for an average user such as content creator"
---

## **USE CASE** 

To instruct an average internet user how to create a page using Hugo Static Site Generator. This guide assumes that Hugo is already installed and configured and Visual Studio Code is installed. The guide refers to this particular user scenario. An example of a user could be a junior Technical Writer. 

## **TIME TO COMPLETE: est. 30 min**

1. Open Visual Studio Code.   
2. Go to Open folder and search for the *`tech-scribe`* folder.  
   ![UI screenshot](/images/hugo-step1.png)

3. From the top menu open a new terminal: `Terminal > New Terminal.`   
   ![UI screenshot](/images/hugo-step2.png)

4. In the terminal, the command to create a new page:  
   	  
   	`hugo new content/posts/your-post.md`

   Replace `your-post` with the name of your post. Insert a hyphen (-) in place of spaces. Keep the `.md` extension.   
   You’ll receive the following message in the terminal once the page is created:  
   	`Content "..." created`

5. Go to the Explorer sidebar, and click on `your-post.md` to select it.   
   The folder and the file are highlighted in green.  
   ![UI screenshot](/images/hugo-step3.png)

6. Hugo creates an empty file containing metadata ( “front matter”) at the top of the page.    
   Example: 

   ```markdown
   ---
   title: "Your Post"`
   date: 2024-11-16T13:56:34+01:00
   draft: true
   ---
    ```

   Replace `true` by false. The page is now no longer in the draft mode   
   and the updates will be visible after the publication. 

7. Add content to your page: paste the text formatted in Markdown you’ve exported from the Google Docs (`File > Download > Markdown`).   
   For Windows: Use `Ctrl + V`  For Mac: `Command (⌘) + V`

8. In the terminal, type `hugo server` to check that the page displays correctly.   
   Hugo builds the page and displays the related messages in the terminal.

9. In the terminal, hover over [http://localhost:1313/](http://localhost:1313/) and then click on   
   `Follow link` to access the preview of the page in the browser.   
   Check if the page displays correctly. 

10. Press `Ctrl+C` to stop the preview. 


**`Result`**: Your page is now ready to be uploaded to GitHub. 

**Next step**: Refer to the *Upload hugo page to GitHub*.   
**Troubleshooting**: Refer to the *Common Hugo Errors*. 

