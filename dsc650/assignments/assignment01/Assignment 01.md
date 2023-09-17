---
title: Assignment 1
subtitle: Computer performance, reliability, and scalability calculation
author: Zachary Campbell
---

## 1.2 

#### a. Data Sizes

| Data Item                                  | Size per Item | 
|--------------------------------------------|--------------:|
| 128 character message.                     | 128 Bytes - assumption is each character is encoded using 1 byte        |
| 1024x768 PNG image                         | 3-4.5 MB - Assuming that each pixel is aprox. 3-5 bytes Image Size times 4 byes divided by number of bytes in a megabyte         |
| 1024x768 RAW image                         | 1.5 MB - Assuming that raw images are approx. 12 bits per pixel 12* size of image divied by 8 * the b to MB conversion         | 
| HD (1080p) HEVC Video (15 minutes)         | 562.5 MB - Assuming that the average bitrate of 8 Mbps * the length of the video         |
| HD (1080p) Uncompressed Video (15 minutes) | 7455 MB - Assuming that there are roughly 24 bits per pixel for a video at 1080p video resolution x rate x bits converted from B to MB      |
| 4K UHD HEVC Video (15 minutes)             | 3375 MB - Assuming that there is an average of 20mbps for the video * the length of the video          |
| 4k UHD Uncompressed Video (15 minutes)     | 29775 MB - Assuming that its 24 bits per pixel and 30 frames per second           |
| Human Genome (Uncompressed)                | 715.255 GB - Assuming that its a 2 bits per base pair and the human genome is approx. 3 billion bases and converting that to GB         |

#### b. Scaling

|                                           | Size     | # HD | 
|-------------------------------------------|---------:|-----:|
| Daily Twitter Tweets (Uncompressed)       | 59.6 GB  |   1  |
| Daily Twitter Tweets (Snappy Compressed)  | 29.6 GB  |   1  |
| Daily Instagram Photos                    | 214.85 GB|   1  |
| Daily YouTube Videos                      | 787.5 TB | 2366 |
| Yearly Twitter Tweets (Uncompressed)      | 217.54 TB |  653|
| Yearly Twitter Tweets (Snappy Compressed) | 10.8 TB | 33  |
| Yearly Instagram Photos                   | 784.2025 TB | 235,261  |
| Yearly YouTube Videos                     | 287,437.5 TB | 862,313  |

1. 500m tweets per day * 128 = 59.6 * 3 = 178.8 GB
2. 2:1 compression so half as large as the previous
3. Based on the 75% assumption .75 * 100m photos per day * 3mb (approx. size) = 214.85 * 3 = 644.55 gb
4. Assume 30 fps HEVC --> 1125MB * 500 videos per minute * 60 * 24 / 1024^3 = 787.5 TB * 3 = 2362.5 tb
5. Assume 365 days --> 365 * 59.6 = 217.54 TB *3 = 652.62 TB
6. ASsume 2:1 compression so 29.6 * 365 = 10.8 TB * 3 = 32.412 TB
7. 214.85 gb * 365 = 784.2025 TB * 3 = 235,260.75 TB
8. 787.5 tb * 365 = 287437.5 tb * 3 = 862,312.5 tb


#### c. Reliability
|                                    | # HD | # Failures |
|------------------------------------|-----:|-----------:|
| Twitter Tweets (Uncompressed)      | 653   |    15      |
| Twitter Tweets (Snappy Compressed) | 33   |     1      |
| Instagram Photos                   | ??   |     5,364       |
| YouTube Videos                     | ??   |     19,661      |

#### d. Latency

|                           | One Way Latency      |
|---------------------------|---------------------:|
| Los Angeles to Amsterdam  | 153.296 ms                 |
| Low Earth Orbit Satellite | 40 ms                 |
| Geostationary Satellite   | 240-279 ms                 |
| Earth to the Moon         | 1,250 ms                 |
| Earth to Mars             | 5-20 minutes            | 

1. https://wondernetwork.com/pings/Los%20Angeles/Amsterdam
2. https://www.omniaccess.com/leo/
3. https://www.satsig.net/latency.htm#:~:text=Geostationary%20satellite%20latency%20and%20time%20delay%20240ms%20%2D%20279ms
4. https://space.stackexchange.com/questions/35590/what-is-the-lowest-latency-achievable-in-reliable-earth-moon-communications
5. https://mars.nasa.gov/mars2020/spacecraft/rover/communications/#:~:text=It%20generally%20takes%20about%205,(DSN)%20antennas%20on%20Earth.
