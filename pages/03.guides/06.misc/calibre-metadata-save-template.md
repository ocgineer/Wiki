## Kavita Save to Disk template

Kavita requires to have series or individual books to be in their own directory. With the following save template you can have Calibre automatically create this folder for you, either by the set series name or the book title if no series is set. The filename of the book itself will be either the name of the series and the index (number) of the series or the title of the book if no series is set.

1. Open the Preferences in Calibre
2. Click on 'Saving books to Disk' (found under Import/Export)
3. Make sure 'Save cover separately' is **unchecked**.
4. Make sure 'Update metadata in saved copies' is **checked**.
5. Make sure 'Save metadata in separate OPF file' is **unchecked**.
6. Adjust the 'Save template' to the following value;

`{series:'ifempty($,field('title'))'}/{series:'ifempty($,field('title'))'}{series_index:0>2s|, Vol. |}`

After having set these settings, Save to Disk will write the selected books to disk as;
- If having set a series: 'The Series Name/The Series Name, Vol. 01.epub'
- If not having set a series: 'The Title of the Book/The Title of the Book.epub'

**IMAGE OF THE SETTINGS INCLUDING FINALIZED TEMPLATE (ITS STILL WIP)**

## Using the Kavita Save to Disk template

1. Select the book(s) you want to export that are ready for Kavita (having set the metadata)
2. Click 'Save to Disk' (the big blue floppy disk).
3. Now select a directory to save to, this can already be the root directory of your Kavita Library!
4. Move the created directories (with books) to your Kavita library root directory, if needed.

Note; Using 'Save only EPUB format to disk in a single folder' will not create a directory for the saved books, which is required by Kavita.

## Adjusting Title Sort in saved directory and filename

By default Calibre will use title_sort when using Save to Disk, this means that, for example in the English language: The, A, An are placed at the end of the title/series, instead at the beginning. If you do not want this for your directory/filename then you can adjust this by doing the following.

1. Open the Preferences in Calibre
2. Click on 'Tweaks' (found under Advanced)
2. Search for the teak: `save_template_title_series_sorting`
3. Edit the teak to: `save_template_title_series_sorting = 'strictly_alphabetic'`

## Adjusting the prefix of the series index

You can modify the prefix of the series_index to adjust the filename to your preference, for example, if you do not like to have ` Vol. ` you can change the template to the following.

`{series:'ifempty($,field('title'))'}/{series:'ifempty($,field('title'))'}{series_index:0>2s| |}`

> Save to Disk result: 'The Series Name/The Series Name 01.epub'

`{series:'ifempty($,field('title'))'}/{series:'ifempty($,field('title'))'}{series_index:0>2s| - |}`

> Save to Disk result: 'The Series Name/The Series Name - 01.epub'
