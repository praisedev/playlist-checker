# IPTV live source batch detection program

## Introduction

### The main function
Perform batch detection of live sources and generate M3U files from high-quality and effective live sources
-Place the live source file to be detected under the playlists folder:
  -Support multiple files
  -Currently supports m3u format files and txt format, see the example under playlists file for details
-The principle of live source detection
  -Test each connection and record the current network delay for that connection. (Refer to https://github.com/EvilCult/iptv-m3u-maker, thanks!)
  -For the same channel (the same name as titile), only the live source with the lowest latency is reserved
-For a valid high-quality live source, output it as an **m3u** file, the file name is the current time.

## How to use the project

This project is developed based on **python3.7**
- The main parameters  
playlist_file ='playlists/'
Live source source file storage path
m3u8_file_path ='output/'
The path where the detected M3U file is stored
delay_threshold = 5000
Response delay threshold, in milliseconds. If this threshold is exceeded, the live source quality is considered poor
-Place a list of live sources to be detected under the ouput file
-python main.py

## Content to be optimized
-Some codes of sqllite storage have not been optimized
-Some m3u format attribute tags are not supported, and there is an exception when reading m3u files
-Currently generating m3u files does not support group tags