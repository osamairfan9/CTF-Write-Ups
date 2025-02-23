**Challenge Name:** The Hawk’s Last Cry

**Difficulty:** Medium

**Description:** 
The Band of the Hawk was betrayed, and their secret communications were intercepted. A mysterious PCAP file contains fragments of their final messages. However, not all secrets are exposed—some are hidden deeper, beyond what simple analysis can reveal.

**Author:** Osama Irfan

1. Open The Hawk’s Last Cry.pcapng in Wireshark.
2. Analyze the stream, you'll find some http packets. Apply the filter to isolate HTTP traffic.
   ![image](https://github.com/user-attachments/assets/9700f04d-c064-4f42-9759-a45b110c1103)

3. Right-click on the relevant packet → Follow → TCP Stream. 
   ![image](https://github.com/user-attachments/assets/3d5f4fd1-aadc-42dd-84ba-64ea7b5c8816)

4. There you'll find a suspicious jpg file.
   ![image](https://github.com/user-attachments/assets/a1140616-6958-4b30-968b-4e8253319744)

5. Sometimes, HTTP headers or unwanted data get mixed with the image bytes. Export Objects may not strip these correctly, leading to broken images.
   
6. Therefore, In the Follow TCP Stream window:
    Set the display format to Raw.
    Save As → image.jpg.

   The image will initially not open as it is broken.
   ![image](https://github.com/user-attachments/assets/22f2ea82-a6d7-4794-a6ea-c6453f8a0876)

8. Open image.raw in a hex editor and look for the jpg headers I am using an online hexeditor: 
   ![image](https://github.com/user-attachments/assets/4254cccf-5f8f-4d43-9086-9ba8a4ccceef)

9. Search for the jpg marker **(FFD8)**
   ![image](https://github.com/user-attachments/assets/087deb62-c1f6-49c3-beda-33964eaa4028)

   Manually trim everything before FFD8 and after FFD9 (jpg markers) and save it or copy everything from FFD8 to FFD9 and save it as Band of Hawks.jpg.
   
    Start of Image (SOI): FFD8
   
    End of Image (EOI): FFD9
    
12. Open Band of Hawks.jpg and look closely for any visible text on the image.
    ![image](https://github.com/user-attachments/assets/afd46081-2784-4edf-a497-7526783fd689)
    
    The text serves as the passphrase for the next step.

14. Use Steghide to extract hidden data from the image, when prompted, use the text found on the image as the passphrase.
     > steghide extract -sf "Band of Hawks.jpg"

    ![image](https://github.com/user-attachments/assets/be62d7b2-3ff8-454e-9982-113d4ea7a7b8)

11. Upon successful extraction, you'll retrieve a secret.txt file containing the flag.
    ![image](https://github.com/user-attachments/assets/3e25716c-ea27-423f-88ed-4dc992d3a5fb)

    (Note: Remove an extra bracket from the flag as it was a typo error.)

12. **Flag:** **AxP25{HawkFallen_BetrayalHiddenInShadows}**
