---
tags:
  - Paper
  - RemoteSensing
Paper Title: No-Reference Hyperspectral Image Quality Assessment via Quality-Sensitive Features Learning
Reference: Remote Sensing | Free Full-Text | No-Reference Hyperspectral Image Quality Assessment via Quality-Sensitive Features Learning,Yang, J., Zhao, Y., Yi, C., & Chan, J. C. W. (2017)
---
#### Summary
The paper aims at assessing the quality of HS images without the need for pristine reference images. The authors do that by computing 5 statistical quality-sensitive features from the pristine and distorted HSIs and compare them to assess the HSI quality. 
#### Distortions
- Gaussian noise with sd=0.05
- Gaussian noise with sd=0.20
- Blurring 3x3a average filtering
- Blurring 5x5 average filtering
#### Statistical Quality-sensitive features
##### Spectral features
1. **Local Spectra normalisation**
	The pristine HSI normalised spectra (luminance) follows a Gaussian distribution while the distorted HSIs' normalised spectra deviates from this distribution distinctively.
	**= Extract distribution features from HSIs: shape and scale params**
	![[Pasted image 20231117114211.png|570]]
	To show that the extracted features are sensitive to the image quality
	![[Pasted image 20231117115042.png|400]]
##### Spatial features
1. **Panchromatic images**
	HSIs usually have a large number of spectral bands. For time optimisation, the authors synthesise the HSI into panchromatic (gray-scale/that reflects brightness of pixels) images. Which are useful for bringing forward the textural properties of an image:
	![[Pasted image 20231117120641.png|200]]
	*I: is the spectral bands corresponding to red, green, blue  ;   w: is the weights assigned to each band* 
	The panchromatic image luminance is then locally normalised.
	The pristine HSI do follow a GGD and the distorted ones deviate
	**= Extract distribution features from the HSIs: shape and scale params**
	![[Pasted image 20231117121550.png|600]]
	- **Log-Gabor filter on panchromatic image**
		To exploit the textural properties of the panchromatic image, the authors apply the Log-Gabor filter to the panchromatic image. Again, different distortions lead to different deviated Gaussian distribution, while the pristine one follows a GGD.
		(Same process)
		**= Extract distribution features from the HSIs: shape and scale params**
		![[Pasted image 20231117130018.png|600]]
	- **Directional gradient of Log-Gabor's response map**
		To further exploit the response features of the Log-Gabor filter, the authors exploit the directional gradient of the response map: the vertical gradient.
		(Same process)
		**= Extract distribution features from the HSIs: shape and scale params**
		![[Pasted image 20231117130632.png|600]]
	- **Gradient magnitude of the Log-Gabor's response map**
		This time, the gradient magnitude of the pristine HSIs follows a Weibull distribution and is deviated for distorted images as well
		**= Extract distribution features from the HSIs: shape and scale params**
		![[Pasted image 20231117130853.png|600]]
##### Proof of Parameter Sensitivity to image quality
![[Pasted image 20231117131055.png|500]]
#### Experiments & Settings
##### Data
In their experiments the authors used 2 datasets:
- AVIRIS sensor data (Moffett Field, Cuprite, Lunar Lake, Indian Piens)
- HyperspecVC sensor data (Chikusei, Ibaraki, Japan)
#### Authors' conclusions

#### Critique/Insights
- How come pristine images features are not clustered in most spatial quality-sensitive features graphs (fig10-12)?
- Play around with the panchromatic conversion formula: are those the only weitghts?
- In our version: maybe keep water absorption bands ?
- Test more types of distortions