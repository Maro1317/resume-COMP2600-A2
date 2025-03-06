# Building and Hosting a Markdown Resume with Pelican and Git  
**(A Practical Guide for Marvin McLaren, Inspired by Andrew Etter’s _Modern Technical Writing_)**

---

## 1. Statement of Purpose
This README provides a **step-by-step guide** for creating and hosting a resume using **Markdown**, **Git**, **Pelican**, and **GitHub** (our “forge”). The instructions follow key principles from Andrew Etter’s _Modern Technical Writing_, highlighting the benefits of a **lightweight markup language**, a **distributed version control system**, a **static site generator**, and a **forge** for hosting.

Our target audience is **Marvin McLaren**, a finance manager with minimal programming experience but growing interest in modern technical writing. These instructions assume Marvin is comfortable with basic Windows commands (like changing directories and running simple commands) but has **no prior experience** with Git or Pelican.

By following this guide, you will:
1) Create and format your resume in **Markdown**.  
2) Use **Git** for version control.  
3) Convert your Markdown resume into a website using **Pelican**.  
4) Host your site on **GitHub Pages** so it’s publicly accessible.  

---

## 2. Prerequisites
Before starting, ensure you have:

1) **Windows PC** (same setup Marvin uses).  
2) **Git** installed – [Download Git for Windows](https://git-scm.com/download/win).  
3) **Python 3** installed – [Python Downloads](https://www.python.org/downloads/) (required for Pelican).  
4) **Pelican** – installed via `pip install pelican markdown`.  
5) **GitHub Account** – [Sign up on GitHub](https://github.com/) if you don’t have one.  
6) **Markdown Editor** (optional) – You can use Visual Studio Code, Notepad++, or any editor that helps with Markdown preview.

These tools follow Etter’s recommendation to use free, widely available solutions that **maximize accessibility**. As Etter notes, modern writing teams should pick tools with minimal overhead, so new contributors (like Marvin) can learn quickly.

---

## 3. Step-by-Step Instructions
The following instructions illustrate how to **format your resume** in Markdown, **generate** a static site with Pelican, and **publish** it on GitHub Pages. Each step shows relevant advice from Etter and references William S. Pfeiffer’s guidelines for creating clear instructions.

### 3.1 Plan Your Markdown Resume  
**(Etter’s Principle: _Use Lightweight Markup_ / Pfeiffer’s Guideline #1 & #5)**

1) **Decide** on the basic sections for your resume (e.g., Education, Work Experience, Projects).  
2) **Create** a new folder named `my-resume` on your Windows PC.  
3) **Open** that folder in a text editor.  
4) **Write** your resume in a file named `resume.md`, using Markdown headings (`#`, `##`) to structure sections. Keep each step simple: one action per line.

**Why This Matters:**  
- **Lightweight markup** like Markdown is simpler than raw HTML, letting you focus on content rather than complicated syntax (Etter’s recommendation).  
- Using **clear headings and lists** follows Pfeiffer’s guidelines for clarity (Guideline #1: technical level) and “one action in each step” (Guideline #5).

### 3.2 Initialize Git  
**(Etter’s Principle: _Use a Distributed Version Control System_ / Pfeiffer’s Guideline #10)**

1) **Open** Command Prompt or PowerShell in the `my-resume` folder.  
2) **Run** `git init` to create a new Git repository locally.  
3) **Stage** the resume with `git add resume.md`.  
4) **Commit** the changes via `git commit -m "Add initial resume in Markdown"`.

**Why This Matters:**  
- **Distributed version control (Git)** saves the entire project history and facilitates collaboration. Etter highlights that teams can branch, merge, and revert changes easily.  
- **Simple style** (Pfeiffer’s Guideline #10) means short, direct steps: “Open,” “Run,” “Stage,” “Commit.”


# Installing Pelican and Generating a Static Site

## 1. Environment Setup
1) Ensure you have [Python 3](https://www.python.org/downloads/) installed.
- Verify `pip` availability with:
  ```bash
  pip --version
-if not avaliable use the command:
  `python -m ensurepip --default-pip`

## 2. Install Pelican and Markdown
  `pip install pelican markdown`

## 3. Create Project Structure

1) After installing Pelican, create a directory for your project.  
2) Run: `pelican-quickstart`  
   This sets up the standard Pelican theme and files.
   
## 4. Generate the Static Site

1) Make a `content` folder (e.g., `mkdir content`) and place your Markdown files (like `resume.md`) inside.  
2) Run: `pelican content`  
   Pelican generates an `output` folder containing HTML files.

## 5. Initialize Git and Commit    
 run the following commands:  
 1)`git init`        
 2)`git add .`       
 3)`git commit -m "Initial commit`  

## 6. Push to a Forge
1) Create a new repository on a hosting service (e.g., GitHub).  
2) Add the remote URL:
`git remote add origin https://github.com/YourUsername/YourRepo.git`
3) Push your code:
`git push -u origin main`

## 7. (Optional) Deploy to GitHub Pages
1) In your GitHub repository, go to **Settings → Pages**.  
2) Under **Source**, select your main branch and save.  
3) After deployment, your site is available at:
`https://YourUsername.github.io/YourRepo/`

## 8. Optional Pelican Configuration
`pelicanconf.py` (created by `pelican-quickstart`) lets you customize settings like theme, site name, author, and more. You can also remove sections (e.g., social links) to tailor your site to your preference.

## Further Resources & Readings

For additional learning and references, explore the following resources:

1) **Markdown Guide** – A comprehensive guide to Markdown syntax and usage.  
   [https://handbook.gitlab.com/docs/markdown-guide/](https://handbook.gitlab.com/docs/markdown-guide/)  

2) **Pelican Documentation** – Official documentation for setting up and using Pelican as a static site generator.  
   [https://docs.getpelican.com](https://docs.getpelican.com)  

3) **GitHub Pages Documentation** – Guide on how to deploy and host static sites using GitHub Pages.  
   [https://pages.github.com](https://pages.github.com)  

4) **Andrew Etter’s _Modern Technical Writing_** – Insightful book on modern documentation practices.  
   [https://www.amazon.com/Modern-Technical-Writing-Andrew-Etter/dp/1365314572](https://www.amazon.com/Modern-Technical-Writing-Andrew-Etter/dp/1365314572)  

## FAQ

### **Q1: Why is Markdown better than writing raw HTML?**
**A:** Markdown is simpler to read, write, and maintain. Instead of cluttering your content with HTML tags, Markdown uses minimal, plain-text syntax. Andrew Etter recommends this approach for anyone new to technical writing or web development because it reduces complexity and makes collaboration easier.

### **Q2: I changed the Markdown version of my resume, so why don’t I see the changes when I refresh my website?**
**A:** You must regenerate the static site (e.g., by running `pelican content`) and push the newly generated files to your forge (e.g., GitHub). Hosting services like GitHub Pages may take a minute or two to reflect updates, so refresh your browser afterward.

### **Q3: What if I want to keep my resume private instead of making it public?**
**A:** You can create a private repository on services like GitHub, but hosting free static sites typically requires a public repository. Paid plans on some forges allow private pages, or you can host the generated HTML elsewhere, like a private server.

### **Q4: Can I use a different static site generator instead of Pelican?**
**A:** Absolutely. Andrew Etter’s core principle is to use *a* static site generator, not necessarily Pelican. You could choose Jekyll, Hugo, or others. The same idea applies: write in Markdown, generate HTML, and host the static files on a forge.

### **Q5: How do I update the look and feel of my resume site?**
**A:** Pelican supports themes. You can either download pre-built themes (e.g., from the Pelican Themes repo) or create your own by modifying the HTML and CSS templates. Just make sure your `pelicanconf.py` points to the correct theme folder.

### **Q6: How can I share my resume offline?**
**A:** You can zip up the `output` folder generated by Pelican and send it to someone. They just need to open `index.html` in a browser. This ensures your resume looks identical to the hosted version, even without internet access.


## Credits

This project was peer-reviewed and improved with the valuable feedback of my group members:

- **[Peer 1 Name]**  
- **[Peer 2 Name]**  
- **[Peer 3 Name]**  

Thanks to the team for their help !

