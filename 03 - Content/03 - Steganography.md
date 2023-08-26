---
creation date: August 26th 2023
last modified date: August 26th 2023
aliases: []
tags: #📖
---

Primary Categories: [[000 - Global Index]] 
Secondary Categories: [[02 - Foundations]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - Steganography]]  

___
# Introduction

Steganography is the art and science of hiding data or messages within other non-secret text or data. The name stems from the Greek words 'steganos' (meaning concealed) and 'graphein' (meaning writing). 
## Historical Use

- **Ancient Greece (440 BC)**: Histiaeus, a Greek historian, used a servant's shaved head to tattoo a hidden message. Once the hair grew back, the servant was dispatched, and the recipient was informed to shave the head again to reveal the message.
- **Invisible Inks**: Over time, messages were written in invisible ink on paper, decipherable only when heated or treated with a particular substance.
- **World War II**: Espionage agents utilized microdots (tiny photographic reductions of large documents) to communicate discreetly. Additionally, photosensitive glass was employed to conceal information.
- **Knitted Messages**: Some messages were written in Morse code on yarn, which was then knitted into clothing.
## Modern Techniques

1. **Image Steganography**: Data is hidden within the least significant bits of images. At a glance, these images appear unaltered.
2. **Social Steganography**: In places with strict censorship, messages are concealed within pop culture references or subtly altered media content.
3. **Audio Steganography**: Secret messages are embedded into digital audio signals. Methods include:
    - **LSB (Least Significant Bit)**: Embeds text data by converting the audio sample into bits. It can increase the capacity for hidden text.
    - **Echo Hiding**: Known for robustness and high capacity, it embeds data using imperceptible echoes.

Examples of modern-day audio steganography include hidden sounds that can activate smart devices like Amazon's Alexa, or high-pitched ringtones that only young individuals can hear.
## Detection

- **Steganalysis**: The practice of detecting steganography, often involving the examination of files for any alterations or oddities. 
- **Stegware**: Refers to cyber-attacks hidden using steganography, making detection even more challenging.
## Tools

Several tools aid in both the creation and detection of steganographic content:

1. **Crypture**: Hides data inside a BMP image file.
2. **Binwalk**: Searches binary images for embedded files, especially within firmware images.
3. **Steghide**: An open-source tool for hiding data inside images or audio files.
4. **rSteg**: Java-based tool for embedding text within an image.
5. **OpenStego**: Allows hiding of various files inside image formats with the output as a PNG.

**Example of Steghide**:

- To inspect an image: `steghide info file.jpg`
  This would provide information about any embedded content.
- To extract data from an image: `steghide extract -sf file.jpg`
## Relevance in Cybersecurity

Steganography is becoming increasingly vital in cybersecurity. Malicious actors leverage it to bypass security defenses, embedding malicious content in seemingly innocent files. Their goal often is data exfiltration from compromised systems without detection.



___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: August 26th 2023 (03:26 pm) 
Last Modified Date: August 26th 2023 (03:26 pm)
