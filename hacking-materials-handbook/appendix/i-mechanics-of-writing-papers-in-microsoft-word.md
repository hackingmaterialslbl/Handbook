# Mechanics of writing papers in Microsoft Word

Many researchers gravitate to LaTeX because of poor experiences with Microsoft Word. With few exceptions, I’ve found the poor experiences to be due to either (i) not using a good template (journal templates are notoriously bad), (ii) lack of knowledge with using MS Word properly - e.g. to reference figure captions or add citations, or (iii) using a very outdated version of Word (i.e., prior to Word 2011).&#x20;

That stated, there are certainly good reasons to use LaTeX as well. Especially when a document has multiple collaborators (all of whom need to add references), I tend to prefer LaTeX plus Overleaf which is supported by LBL: [_https://www.overleaf.com/org/lbl_](https://www.overleaf.com/org/lbl) . The Overleaf tool keeps getting better making LaTeX very attractive these days.&#x20;

For now, let’s stick with Word unless there’s good reason not to. Here’s how to write a good-looking, easy-to-manage manuscript in Word. Note that some of the instructions may differ slightly depending on your version of Word.&#x20;

### Start with a visually attractive template&#x20;

Rather than using journal templates, which are often buggy (and the source of many frustrations with Microsoft Word), it is better to write and modify your manuscript using the group’s template. To get started, download the style from [_https://hackingmaterials.lbl.gov/stuff/word\_styles\_v3.zip_ ](https://hackingmaterials.lbl.gov/stuff/word\_styles\_v3.zip)and start writing in “AJ\_paper\_v3\_example.docx” and save it as your own file (alternatively, you can install the style file or template file included in that zip archive). If the document looks strange, you may be in outline view: simply go to View and click on Print Layout, then adjust the zoom level to your liking (for large monitors, I often prefer two pages on the screen).

### Add sections and subsection headings properly&#x20;

In the “Home” tab, there are various types of formatting styles including Normal, Heading 1, Heading 2. To fully take advantage of this feature make sure that you enter main section headings with Heading 1, your subsections with Heading 2, and all main body text with Normal. In this way, headings will renumber themselves as needed as you add more headings and sub-headings. To reference a particular section, use the “cross-referencing” feature described later in this document (do not just manually type out the section/subsection name or number). Such cross-references will automatically update as headings change.&#x20;

#### Insert figures and tables and their captions properly&#x20;

Use the following procedure to insert and place figures and tables:

1. At the desired point in your manuscript, start a fresh line of text and insert your figure or table using the Insert->Photo or Insert->Table command (or drag/drop a figure from your file system, or copy-paste a table from Excel, etc..)
2.  Right-click on the object and then select “Insert Caption” (choose the proper label; e.g. Figure 1 vs Table 1) in the next line and write your caption. Note that these captions will

    auto-update and auto-renumber.
3.  (optional). If you want to resize or reposition your figure/table and caption, then with your mouse select both the object and the caption and then Insert > Text Box: Now the object and its caption should be nicely fit into a text box which you can simply move to different places in your document using your mouse. The text box is particularly helpful when writing in formatted

    documents as it can be moved to your desired location. Furthermore, there are formatting options in the text box that allow the text to flow around the text box in your desired style (right-click the entire text box and select from the various “Wrap Text” options).

To refer to a figure or table in the main body of the document so that numbering is handled automatically, see the next section on cross-referencing objects.&#x20;

#### Insert equations and equation numbers properly&#x20;

In earlier versions of Word, it was a pain to add equation numbers. In Word 2016 or greater, it is thankfully very simple:

1. Navigate to the point in the document where you want to insert an equation
2. Insert an equation and write out your equation using the Equation Editor tool
3. Staying within the equation, go to the end of the equation and type a space followed by #(1).
4. Hit “enter” to complete the equation

Word will automatically number your equation.&#x20;

For more, including automatic numbering, see this link (and in particular the response from “Chris C”):[ _https://bit.ly/2JccLG5_](https://bit.ly/2JccLG5)



### Cross-referencing objects: sections, subsections, figures, tables

When referring to a section, subsection, figure, or table in your main body text, it’s important that any numbers and/or quoted text are automatically updated so that you don’t need to manually change these references (e.g., do not manually type “Figure 1” in the text!!). Instead, to cross-reference items:

1. Go to References > Cross-reference
2. Choose your Reference type first (e.g Figure) and choose “Only label and number” under “Insert reference to:” part and then click on Insert. The cross-references that are created this way should be updated automatically even after you add or remove an object of the same type before the current object. Note that there are multiple styles of cross-reference - e.g., number only, label and number, etc.&#x20;

Such cross-references will automatically renumber/update as needed. In rare cases, Word fails to automatically renumber/update cross references. The easiest way to force a refresh is to open the “Print Preview” dialog.

#### Citing articles&#x20;

We suggest the use of Zotero to organize your research library and to insert citations into Microsoft Word via the Zotero plug-in (or perhaps create a BibTeX library for use with LaTeX). See the Zotero documentation for more details.

### Troubleshooting&#x20;

When you move equations, tables, and figures around the caption numbering should automatically update to reflect their positions in the document. If this does not happen in your cross-references, go to File > Print, then close out of the print menu (without printing). This can fix issues of cross references not updating on-the-fly. This trick may make take a couple tries to work.
