# ACES-1.2.0-OCIO-v1-config-with-ARRI-LogCv4
Author: Jakub Matejka

ACES 1.2.0 config with ARRI LogCv4 added

ARRI LogCv4 is officially supported in ACES 1.3 OCIO 2.x configs.
So I made a custom OCIO 1.x config with LogCv4.

As a base, I used the ACES 1.2.0 config from:
https://github.com/colour-science/OpenColorIO-Configs

For building ACES source code, I used this article/tutorial from Nathan Inglesby: 
https://www.postwork.io/blog/2021/7/6/creating-an-f-log-colorspace-for-the-aces-ocio-config-in-nuke

I tried to build ACES 1.2, but I could not figure out the right dependencies - fixed 1, broke 1.
So I sticked with Nathan's Docker build for ACES 1.1. For my purpose it does not matter, because from this build I only wanted to generate .spi1d LUT LogC4_to_Linear.spi1d. Than I copy LogCv4 color space definition from this 1.1 build to ACES 1.2.0 oficial config a little modified it.

For LogCv4 definition, I used an official document from ARRI:
https://www.arri.com/resource/blob/278790/bea879ac0d041a925bed27a096ab3ec2/2022-05-arri-logc4-specification-data.pdf

And for the color space conversion matrix, I used this calculator from Harald Brendel - Head of the Image Science Team at ARRI:
http://color.support/colorspacecalculator.html

Update:

-Add AppleLog support. For Lin 2 Log I used official LUT and for the color space conversion matrix I used the same calculator. The right coordinates I found in Apple Log Profile White Paper (September 2023)
