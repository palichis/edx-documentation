.. _Uploading Videos in Studio:

###########################
Uploading Videos in Studio
###########################

After a video administrator works with the edX media team to complete
:ref:`preliminary setup<Video Getting Started>` for the entire institution,
individual course teams can begin to upload video files for their courses in
Studio. This section describes the specifications met by successful video
files, the steps to upload the files, and how you monitor video processing 
at edX.

.. removed "how course teams enable the video upload process in Studio, " 

* :ref:`Specifications for Successful Video Files` 

* :ref:`Upload Video Files`  

* :ref:`Monitor Video Processing`

The result of video processing is additional file formats that are transferred
to multiple hosting services (YouTube CMS and Amazon AWS), ready for students
to access.

.. _Specifications for Successful Video Files:

***************************************************
Specifications for Successful Video Files
***************************************************

Your videos can contain whatever content you want to include in the course.
The `Creating Videos`_ section of `edX101 Overview of Creating an edX Course`_
has some helpful pointers for creating good video content.

=========================
Supported Video Formats
=========================

The automated processing that takes place at edX transforms each of your
uploaded video files into several different formats. For this process to
succeed, you must upload videos in **.mp4** or **.mov** format.

===========================
Compression Specifications
===========================

For best results, your video files should have these compression specifications.

.. list-table::
   :widths: 40 40
   :stub-columns: 1

   * - Codec & Container
     - H.264, .mp4
   * - Resolution & Frame Rate
     - 1920x1080, progressive, 29.97 fps (see note)
   * - Pixel Aspect Ratio
     - 1.0
   * - Bit Rate
     - VBR, 2 pass
   * - Target VBR
     - 5 mbps
   * - Max VBR
     - 7.5 mbps
   * - Audio
     - AAC 44.1 / 192 kbps

.. note:: Typically you export at the same frame rate that was used when you 
 created the media file. For example, if you create the file in a country that
 uses the PAL system, you export at 25 fps instead of the NTSC standard of
 29.97 fps.

.. _Enable Video Upload in Studio2:

.. ******************************
.. Enable Video Upload in Studio
.. ******************************

.. This procedure needs to be completed only once per course in Studio.

.. #. Work with your institution's video administrator to obtain the edX video
   identifier for your course. The edX media team defines a unique video
   identifier for each course.

.. #. Open the course in Studio. 

.. #. Select **Settings**, then **Advanced Settings**.

.. #. In the **Video Upload Credentials** field, place your cursor between the
   supplied pair of braces.

.. #. Type ``"course_video_upload_token": "xxxx"`` where ``xxxx`` is the unique
   edX identifier for your course. This ID value is an 8-20 character hash
   string.

.. #. Click **Save Changes**. Studio reformats the name:value pair you just
   entered to indent it on a new line.
   
 .. image:: Images/Enable_video_upload.png
  :alt: Video Upload Credentials field with the course_video_upload_token
      policy key and a token value

.. #. Refresh your browser page. The Studio **Content** menu updates to include
   the **Video Uploads** option.

.. Team members can then begin to :ref:`upload video files<Upload Video Files>`.

.. _Upload Video Files:

***************************
Upload Video Files 
***************************

Before you can upload video files, the video upload feature must be enabled
for the course. Your video administrator coordinates this task with the edX
media team. See :ref:`Create YouTube Channels`.

#. Open the course in Studio. 

#. Select **Content**, then **Video Uploads**.

#. Add video files to the **Video Uploads** page. You can drag files to the
   page and drop them, or click **Select files** to locate the files to
   upload.

   A rectangular tile appears on the page for each file. The file name, a
   progress bar, and the status of the file upload process appear in the tile.

.. how many files can be uploaded at once
.. what kind of bandwidth/connection is recommended

.. You can use your browser to navigate to other pages while upload is in progress. Return to the Video Uploads page periodically to refresh the status for each file.

.. important:: You must leave the **Video Uploads** page open in your
   browser until the upload process is complete for all files.

The file upload process is complete when files upload successfully or fail to
upload. You can monitor file progress on the **Video Uploads** page or
download a report.

.. _Monitor Video Processing: 

***************************
Monitor Video Processing
***************************

After your video files successfully reach the edX servers, automated
processing begins. 

.. note:: Automated processing takes 24 hours to complete.

A list of every file that you attempt to upload to the edX servers appears in
the **Previous Uploads** section of the **Video Uploads** page. The list
includes each file's status in the encoding and hosting workflow. In addition,
you can download a report of the video files that you uploaded. See
:ref:`Reporting Video Status`.

.. _Video Processing Statuses:

===========================
Video Processing Statuses
===========================

The encoding and hosting process assigns these statuses to video files.

* **Uploading** files have not yet reached the edX servers successfully. For
  files that encounter a problem, verify that the file that you uploaded is in
  .mp4 or .mov format and meets the other specifications for successful video
  processing. See :ref:`Specifications for Successful Video Files`. Then try
  uploading the file (or its replacement) again.

* **In Progress** files are undergoing processing to create additional file 
  formats or waiting for successful transfer to the host sites.

* **Complete** files are ready for inclusion in your course and for students to
  view. See :ref:`Adding Videos to a Course`. When you click the names of these
  files, a file hosted on one of the external host sites plays.

* **Failed** files did not complete processing successfully. Verify that you
  can play your original .mp4 or .mov file and that it meets the other
  specifications for successful video processing. See :ref:`Specifications for
  Successful Video Files`. Upload the file, or a replacement file, again. If
  processing fails more than once for a file, contact the edX media team at
  media@edx.org.

Statuses of **Invalid Token** or **Unknown** indicate  a configuration
problem. Inform your edX program manager if these statuses appear.

.. add an xref to the TBD overview section on the edX transcode-and-host process

.. _Reporting Video Status:

================================
Reporting Video Statuses
================================

To report the status of the encoding and hosting process of every video file
that you upload, as well as the assigned video IDs, you can download a CSV
file.

#. Open the course in Studio. 

#. Select **Content**, then **Video Uploads**.

#. Click **Download available encodings (.csv)**.

#. Use a spreadsheet application or text editor to open the CSV file.

The CSV file reports data in these columns for all of the files you upload.

* The file **Name**.

* The file **Duration**. If the upload process has not yet determined how long
  the file is, **Pending** appears.

* The **Date Added**, which shows the date and time that you uploaded the
  video file.

* The unique, identifying **Video ID**. When you add a video component to your
  course, you supply the video ID for the file you want to add. See
  :ref:`Adding Videos to a Course`.

* The **Status** of the encoding and hosting process for the file. See
  :ref:`Video Processing Statuses`.

The CSV file also includes a column for each of the formats and host sites
that are the result of the edX encoding and hosting process. The CSV file
includes data in these columns only after each format is successfully
generated and delivered to its destination.

* **desktop_mp4 URL**: The AWS location of a 720p resolution video file in mp4
  format. This file is delivered to students who do not have access to YouTube
  and view course videos with an mp4 player.

* **desktop_webm URL**: The AWS location of a 720p resolution video file in
  webm format. This file is delivered to students who do not have access to
  YouTube and view course videos with a webm player.

* **mobile_low URL**: The AWS location of a 320p resolution video file. This
  file is delivered to students who download and view course videos on a
  mobile device.

* **youtube URL**: The YouTube location of a 1080p resolution video. By
  default, the edX video player delivers this video.

The edX encoding and hosting process produces these alternatives to ensure
optimal playback quality for your students. 


.. _Creating Videos: https://courses.edx.org/courses/edX/edX101/2014/courseware/c2a1714627a945afaceabdfb651088cf/9dd6e5fdf64b49a89feac208ab544760/

.. _edX101 Overview of Creating an edX Course: https://www.edx.org/node/5496#.VH8p51fF_FA
