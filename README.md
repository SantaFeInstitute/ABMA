# ABMA Website 
These are website maintenance instructions for the Agent-Based Modeling for Archaeology website.

## An overview
The website theme code is accessed through `ABMA/config.yml`. Here we have used the Jekyll theme "Minimal", which is called in `theme: jekyll-theme-minimal`. The title of the of the website (that appears in the main section, not the left sidebar) is called in `title: Agent-Based Modeling for Archaeology`. We use `logo:` to create the picture in the sidebar. We use `show_downloads: false` so that any GitHub, ZIP File, or TAR Ball downloads that might show up do not actually show up (we needed to save space to have all of the chapter headings in the sidebar). **All code** needs to be written in HTML to render properly on the website (using Markdown language gives the proper result in the preview of the specific file but does not translate correctly when the website is published).

**HTML vs. Markdown:** It is very important to note that all of the code is written in HTML but in a Markdown document (`index.md`). If the code is copy-pasted as is and put into an HTML document (`index.html`), it breaks the website formatting and leaves lines of text with pictures in a disorganized manner. If the code is rearranged into purely HTML, it will need to look something like the formatting of `default.html`.

## How to change/edit the website files
To make changes to the website, navigate through `SantaFeInstitute` --> `ABMA` and select `gh-pages` from the **master** dropdown above the individual chapter folders. (If you are here, you have already done that. Congratulations!)

To change a specific file, click on the file name (the farthest left text of the three columns, for example `_config.yml`). When you hover your cursor over the title, it will turn blue to signify that it is clickable. The text in the middle column, that will say something like "Update README.md", tells you the last thing that happened to the file; in this example case, it means that the `README.md` was updated however long ago is shown in the right column (ex. "3 months ago"). You have the option to change the text in the middle column to more specifically reflect what happened to the file by altering the text at the bottom of the page (when you are editing the file) in the "Commit changes" box that has one short gray text box and one longer gray text box; the first box will say "Update README.md" because that is the default text that appears when any file is updated (with whatever shows up in the `README.md` space differing depending on the file name/type), and you can highlight that text and replace it with whatever you choose (for example, "updated figures", "updated sidebar Ch. 10 title", etc.).

## General changes to the static sidebar
To make changes to the static sidebar on the left-hand side of the website, stay in the `ABMA` section, go to the layouts folder `_layouts`, and select the `default.html` document. In order to make and save changes to the sidebar, you will need to click on `default.html` and then the pencil icon in the upper right-hand corner of the light gray bar above the html text. Any changes that you make will need to be saved by clicking on the green "Commit changes" button at the bottom of the page (leave the button next to "Commit directly to the `gh-pages` branch." selected). 

## Changing text color, background color, and text
The following code changes the text and color of the header at the top of the left sidebar. 

To change the text color, you need to change the html color hexcode; the current hexcode in use (`"#000000"`) makes the text black. You can search Google to find lists of different hexcodes that correspond to pretty much every color in existence. 

To add a background color behind the text, add in `style="background-color: #000000"` (in this instance the zeros will make the background color black). The complete code with a background color added would look like this:` <p style="background-color: #000000" style="color: #000000">`. 

Change the text by changing the text of "Agent-Based Modeling for Archaeology" in the following section: `<Agent-Based Modeling for Archaeology</p>`, which appears here in the full formatting: \
        `<h1>` \
          `<p style="color: #000000">Agent-Based Modeling for Archaeology</p>` \
        `</h1>` 

## Anchors
The anchors on the sidebar are put in place with the following code:

(1)      `<a style="color: #E66100" href="#INTRODUCTION">Ch. 0 • Introduction</a>` \
(2)      `<a href="path/to/contributing/index.md#INTRODUCTION">`
      
The text "Ch. 0 • Introduction" in `>Ch. 0 • Introduction</a>` will appear in the sidebar as a clickable link. The `href="path/to/contributing/index.md#INTRODUCTION">` is the code that makes the anchor work (directing the click to the "INTRODUCTION" section). This references the following code in the `index.md` (the section that contains the body of the website) where we named the introductory section:
  
(3)      `<a name="INTRODUCTION"></a>` \
(4)      `### INTRODUCTION: The Art & Science of Building Societies in Silico`

The above code (3 and 4), along with the `href` part of (1), relies on the `name="INTRODUCTION">` being *above* the actual Introduction title in order for the anchor to redirect to the title. If `name="INTRODUCTION">` were located underneath the actual Introduction title, the anchor redirection would omit the title and direct the readers straight to the chapter description. 

## Making clickable links
To make text clickable, we use the code below. First we set the color of the text (can be easily changed as discussed above in the color section). Next we use `href="website"`—copy the link in place of the placeholder `website`. Adding `target="_blank"` means that the link will open in a new tab, not the one that is displaying the website. The color, link, and target specifications all go together in the first `<a >`, followed by the text that we want to be clickable (in this case "Chapter as PDF"), followed by `</a>` to close out the code.

<u> Example code: </u> \
`<a style="color: #E66100" href="https://github.com/SantaFeInstitute/ABMA/blob/master/book/ABMA_Conclusion.pdf" target="_blank"> Chapter as PDF </a>`  

## Clickable images
Making a clickable image is very similar to making a clickable link, except now we need to replace the specified clickable text with an image source. 

The first code included in `< >` is identical to the code in the section above ("Making clickable links"), where we placed our link and specified that it will open in a new tab. Next we need to identify our image source, which in this case is a url (we did this by adding the images to their own pages in Squarespace); the image source needs "https://" in order to show up (if it is coded based on an image's presence on a specific computer, that would be dangerous because the picture could be deleted and I also couldn't figure out how to do that). `align` specifies left, right, or center alignment of the image, and after `style` we include margin size as well as width and height of the image (easily adjustable). In `alt` we provide alternate text that will show up if the image does not. Finally, we close our code with `</a>`.

<u> Example code:</u> \
`<a href="https://www.sfipress.org/books/agent-based-modeling-archaeology" target="_blank"> <img src="https://images.squarespace-cdn.com/content/v1/5d420e5d999d0200013d33c3/1624392531622-KBOK27QOQTS8OP5R2JSG/ABMA_cover_web-600.png?format=1000w" align = "left" style="margin: 0px 20px 0px 0px; width:300px;height:400px;" alt="Textbook Cover"> </a>`

## Expandable lists (dropdowns)


<u> Example code: </u> \
`<details>` \
`<summary>` \
Click here to expand the list of external resources. \
`</summary>` \
 `<br>` \
 `<ol>` \
 ` <li> <a style="color: #E66100" href="https://ccl.northwestern.edu/netlogo/download.shtml" target="_blank"> NetLogo </a> </li>` \
  This textbook uses NetLogo, a multiagent programmable modeling environment created by Uri Wilensky and developed at Northwestern's Center for Connected Learning and Computer-Based Modeling (CCL). Click the "NetLogo" link to download NetLogo. \
  `</ol>` \
`</details>`


