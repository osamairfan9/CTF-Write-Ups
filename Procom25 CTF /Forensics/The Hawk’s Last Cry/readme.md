**Difficulty:** Medium

**Description:** 
The Band of the Hawk was betrayed, and their secret communications were intercepted. A mysterious PCAP file contains fragments of their final messages. However, not all secrets are exposed—some are hidden deeper, beyond what simple analysis can reveal.

**Author:** Osama Irfan

1. Open The Hawk’s Last Cry.pcapng in Wireshark.
2. Analyze the stream, you'll find some http packets. apply the filter to isolate HTTP traffic.
   
4. There you will find a suspicious jpg file. Right-click on the relevant packet → Follow → TCP Stream.
   
6. In the Follow TCP Stream window:
    Set the display format to Raw.
    Save As → image.jpg.
   ![image](https://github.com/user-attachments/assets/22f2ea82-a6d7-4794-a6ea-c6453f8a0876)

7. ![image](https://github.com/user-attachments/assets/4254cccf-5f8f-4d43-9086-9ba8a4ccceef)

8. Open image.raw in a hex editor and look for the jpg headers I am using an online hexeditor:
   ![image](https://github.com/user-attachments/assets/087deb62-c1f6-49c3-beda-33964eaa4028)

    Start of Image (SOI): FFD8
    End of Image (EOI): FFD9
    
10. Copy everything from FFD8 to FFD9 and save it as Band of Hawks.jpg or another method to remove every header before FFD8 and save it as Band of Hawks.jpg.
    
12. Open Band of Hawks.jpg and look closely for any visible text on the image.
    
The text serves as the passphrase for the next step.

14. Use Steghide to extract hidden data from the image:
 > steghide extract -sf "Band of Hawks.jpg"

9. When prompted, use the text found on the image as the passphrase.
    
11. Upon successful extraction, you'll retrieve a secret.txt file containing the flag.
    ![image](https://github.com/user-attachments/assets/1e619ea0-c8fc-4a6f-8759-4c8c1ecba7b3)
    (Note: Remove one bracket from the flag as it was a typo error.)

