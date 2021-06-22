---
Type:            article
State:           [ draft ]
Title:           Audio Codecs
Project:         HandBrake
Project_URL:     https://handbrake.fr/
Project_Version: Latest
Language:        English
Language_Code:   en
Authors:         [ Scott (s55) ]
Copyright:       2021 HandBrake Team
License:         Creative Commons Attribution-ShareAlike 4.0 International
License_Abbr:    CC BY-SA 4.0
License_URL:     https://handbrake.fr/docs/license.html
---

Audio Codecs
============

 

Encoding vs Passthrough
-----------------------

HandBrake supports two modes of operation for handling audio tracks from the
source.

It can either:

-   Re-Encode the track into a new format. For example, AC3 or DTS audio from a
    DVD or BluRay into AAC for playback on mobile devices.

-   Passthru copies the audio track from the source to the newly encoded file.

 

Audio Encoders
--------------

-   AAC:

    -   Advanced Audio Coding (AAC) is one of the most popular formats available
        in HandBrake and is widly supported by media players and mobile devices.

    -   On Linux and Windows, HandBrake uses the FFmpeg AAC encoder.

    -   On Mac, HandBrake uses Apple's CoreAudio AAC encoder. It's known to be
        much better quality and is the default option for Mac users.

-   HE-AAC (Mac Only)

    -   High Efficiency AAC encoder. This encoder is optimized for low-bitrate
        applications which may be useful for streaming.

    -   Available on Mac only.

-   MP3:

    -   HandBrake also offers the MP3 audio codec, for which it uses the very
        well-regarded lame encoder.

-   Vorbis:

    -   HandBrake offers Vorbis audio encoding as well, for which it uses the
        aoTuV branch that offers quality tweaks.

-   AC3 and E-AC3:

    -   HandBrake can encode to AC3 using FFmpeg.

    -   This is not the same as Passthru. You can encode any audio track to AC3.

-   Opus (FFmpeg)
    
    -   Available in MKV files.

-   Flac 16 and 24bit (FFmpeg)

    -   Lossless audio compression.

    -   Available in MKV files.

    -   It is not currently possible to passthru the compression level to the
        ffmpeg encoder which is currently defaulted to "5"
        
-   Opus:
    
    -   Successor to Vorbis.
    
    -   HandBrake currently uses libopus 1.3.1 for Opus encoding.
    
    -   Designed to have the greatest audio quality at the lowest bitrate.
        
    -   Recent codec, initial release was in 2012 - cutting edge but lacks
        ubiquitous support of older formats such as AAC.
        
    -   Opus is currently supported in VLC, mpv, ffmpeg, Android 5.0+ and iOS 11+
        (this list is not exhaustive).

 

Passthru options.
-----------------

HandBrake supports passthru for a limited number of popular source formats.
These are: AC3, E-AC3, DTS, DTS-HD, TrueHD, MP3, MP2, AAC or flac (Passthru)

This copies the audio bit-for-bit from the source so offers no loss in audio
quality. These audio tracks can be quite large so can impact the final size of
the output file quite substantially.

 

Auto Passthru
-------------

In the audio encoders list, there is an option called "Auto Passthru". When
encoding, this will automatically passthru any supported format to the source
file. If the source format is not supported, or not supported in the output
container, the fallback encoder will be used. The default is AAC.
