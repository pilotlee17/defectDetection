# 基于相位变换的无监督表面缺陷检测软件

本方法通用性强，适合多种纹理表面的缺陷检测，且其实现无需表面纹理的先验信息，也无需借助学习过程。

![Thumbnail Image](results/Main.png?raw=true)

*\*State of the art as of August 2019 in the real-time anime 4K upscaling category, the fastest at achieving reasonable quality. We do not claim this is a superior quality general purpose SISR algorithm compared to machine learning approaches.*

***Disclaimer: All art assets used are for demonstration and educational purposes. All rights are reserved to their original owners. If you (as a person or a company) own the art and do not wish it to be associated with this project, please contact us at 	anime4k.upscale@gmail.com and we will gladly take it down.***

![Comparison](results/Comparisons/1_time.png?raw=true)

## Notice

### This current README is outdated. I don't have the time to update the preprint and the comparisons for the major changes to the algorithm in the latest stable v2.1 version yet. Most issues related to aliasing and texture loss are solved in the latest version of the algorithm. A more rigorous and in-depth preprint is coming soon.

We understand that this algorithm is far from perfect, and are working towards a hybrid approach (using Machine Learning) to improve Anime4K. 

The greatest difficulties encountered right now are caused by these issues that other media does not suffer from:

 - Lack of ground truth (No True 4K Anime)
 - Few true 1080p anime (Even some anime mastered at 1080p have sprites that were downsampled)
 - Non-1080p anime are upsampled to 1080p using simple algorithms, resulting in a blurry 1080p image. Our algorithm has to detect this. (Main reason why waifu2x does not work well on anime)
 - UV channels of anime are subsampled (4:2:0), which means the color channels of 1080p anime are in fact 540p, thus there is a lack of 1080p ground truth for the UV channels.
 - Simulating H.264/H.265 compression artifacts (for analysis and denoising) is not trivial and is relatively time-consuming.
 - Due to the workflow of animation studios and their lack of time/budget, resampling artifacts of individual sprites are present in many modern anime.
 - Speed (preferably real-time) is paramount, since we do not want to re-encode video each time the algorithm improves. There is also less risk of permanently altering original content.
 - So on...

However, we still believe by shrinking the size of VDSR or FSRCNN and using an hybrid approach we can achieve good results.  
Stay tuned for more info!
