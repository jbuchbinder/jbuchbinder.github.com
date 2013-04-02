---
title: Creating TTS Prompts for Asterisk with Realspeak
author: jeff
layout: post
permalink: /2006/05/19/creating-tts-prompts-for-asterisk-with-realspeak/
categories:
  - Hacks
---
# 

I was playing around with using ScanSoft Realspeak for Linux, and finally found the “magic sequence” to generate the appropriate GSM prompts for Asterisk.

Requires: 
*   Standard installation of Scansoft Realspeak 4 with American English Jill voice
*   Debian’s libgsm-tools and sox

`
cd /usr/local/ScanSoft/RealSpeak_4.0
echo " - TTS being performed on $1 ... "
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/usr/local/ScanSoft/RealSpeak_4.0/api/lib
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/usr/local/ScanSoft/RealSpeak_4.0/speech/components/common/
./standard "American English" Jill ./speech text.txt
echo " - Converting to 8000Hz WAV ... "
sox -r 8000 -t raw -w -s /usr/local/ScanSoft/RealSpeak_4.0/standard.pcm text.wav
sox text.wav text.au
cat text.au | toast -c -s > text.gsm
`