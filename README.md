# nSPListUpload

**nSPListUpload** is an easy to use pure HTML WebPart for OOB SharePoint lists that lets you create fields that let users provide URLs or attach/upload files.

## Table of Contents

 1. [Overview / Features](#user-content-overview--features)
 2. [Screenshots](#screenshots)
 3. [Compatibility](#compatibility)
 4. [How To Use](#how-to-use)
  1. [Configure The List](#configure-the-list)
  2. [Add **nSPListUpload** To The List](#add-nsplistupload-to-the-list)
  3. [List Configuration Options](#list-configuration-options)

## Overview / Features

I needed a list where users would provide the URL to a file or image. I wanted the user to be able to provide either a URL to a file that already exists online **or**  upload a file and then the field would use it's path as the URL.

OOB SharePoint lets you attach a file to an item but there was no way to require it. So the user was left with either manually uploading the file somewhere or attaching it to the list and then using its URL for the field.

This was not as elegant as I liked so **nSPListUpload** was born.

With **nSPListUpload** the `NewForm.aspx` and `EditForm.aspx` forms for a list will show a file browse input for the field along with a textarea. If the user selects a file it will attach the file to the list and use the attached file's URL as the field value.

 - For `NewForm.aspx`, if the user attaches a file, **nSPListUpload** will do a redirect after the item is saved to find the ID of the item created and then it will update the field values for the attached files.
 - For `EditForm.aspx`, if the user attaches a file, **nSPListUpload** will use the ID of the item to figure out the URL of the attached file.

# Screenshots

Screenshot | Description
--- | ---
<img src="https://cloud.githubusercontent.com/assets/83817/8394100/a2717fd0-1cf7-11e5-99ea-b54b2fbf20d2.png" height="100px"> | This is before you use **nSPListUpload**. The "Read More File", "Background Image File", "Posting URL or File", and "Headshot URL or Image File" are the fields I want to change.
<img src="https://cloud.githubusercontent.com/assets/83817/8394101/a27cc2a0-1cf7-11e5-90df-f51c924d7e80.png" height="100px"> | This is after you use **nSPListUpload**. All the fields with "file" will have a file browse input added. Fields that have URL will also let the user provide a URL directly.
<img src="https://cloud.githubusercontent.com/assets/83817/8394102/a27f8580-1cf7-11e5-8dce-4d59debba936.png" height="100px"> | This is as you're filling a `NewForm.aspx` or `EditForm.aspx`. Images will render in the form.
<img src="https://cloud.githubusercontent.com/assets/83817/8394103/a27fdd50-1cf7-11e5-9017-0532cc7ebe47.png" height="100px"> | For `NewForm.aspx` the page will redirect to do some post-processing after the item is saved.
<img src="https://cloud.githubusercontent.com/assets/83817/8394104/a281552c-1cf7-11e5-9c3f-dd94e65f4843.png" height="100px"> | This is the `DispForm.aspx`.
<img src="https://cloud.githubusercontent.com/assets/83817/8394105/a282eca2-1cf7-11e5-91d8-47d6e668a3cf.png" height="100px"> | This is the `EditForm.aspx`. Fields that had attached files will let you delete them.

## Compatibility

I only have a trial version of **SharePoint 2010 Foundation** on a VM with **IE 11** and **Chrome 43** so that is all I've been able to test on. If anyone tests on other SP versions and/or browsers and is willing to test for me that would be appreciated.

## How To Use

To use **nSPListUpload** you need to add fields to a list with specific strings in the field name and then add a WebPart to the `NewForm.aspx`, `EditForm.aspx`, and optionally `DispForm.aspx`.

### Configure The List

 1. add a field to your list with "file" (case insensitive) in the field name
 2. check the [table](#list-configuration-options) below for other configuration options

### Add **nSPListUpload** To The List

 1. download and upload the `nSPListUpload.1.0.html` or `nSPListUpload.1.0.min.html` file to your SharePoint site
 2. add a CEWP Web Part to the **bottom** of `NewForm.aspx`, `EditForm.aspx`, and optionally `DispForm.aspx` and reference

### List Configuration Options

Include In Field Name | Action/Result
--- | ---
image | image fields will render the image in the form
url | lets the user direct enter a URL along with uploading a file

** Note: options are case insensitive*
