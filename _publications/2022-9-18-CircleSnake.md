---
title: "CircleSnake: Instance Segmentation with Circle Representation"
collection: publications
permalink: /publication/2022-9-18-CircleSnake
excerpt: 'This paper describes a novel method for instance segmentation within medical imaging.'
date: 2009-10-01
venue: 'IEEE Transactions on Medical Imaging'
paperurl: 'https://arxiv.org/pdf/2211.01254.pdf'
citation: 'Nguyen, E.H., Yang, H., Asad, Z., Deng, R., Fogo, A.B., Huo, Y. (2022). CircleSnake: Instance Segmentation with Circle Representation. In: Lian, C., Cao, X., Rekik, I., Xu, X., Cui, Z. (eds) Machine Learning in Medical Imaging. MLMI 2022. Lecture Notes in Computer Science, vol 13583. Springer, Cham. https://doi.org/10.1007/978-3-031-21014-3_31'
---
## Abstract:
Circle representation has recently been introduced as a “medical imaging optimized" representation for more effective instance object detection on ball-shaped medical objects. With its superior performance on instance detection, it is appealing to extend the circle representation to instance medical object segmentation. In this work, we propose CircleSnake, a simple end-to-end circle contour deformation-based segmentation method for ball-shaped medical objects. Compared to the prevalent DeepSnake method, our contribution is threefold: (1) We replace the complicated bounding box to octagon contour transformation with a computation-free and consistent bounding circle to circle contour adaption for segmenting ball-shaped medical objects; (2) Circle representation has fewer degrees of freedom (DoF = 2) as compared with the octagon representation (DoF = 8), thus yielding a more robust segmentation performance and better rotation consistency; (3) To the best of our knowledge, the proposed CircleSnake method is the first end-to-end circle representation deep segmentation pipeline method with consistent circle detection, circle contour proposal, and circular convolution. The key innovation is to integrate the circular graph convolution with circle detection into an end-to-end instance segmentation framework, enabled by the proposed simple and consistent circle contour representation. Glomeruli are used to evaluate the performance of the benchmarks. From the results, CircleSnake increases the average precision of glomerular detection from 0.559 to 0.614. The Dice score increased from 0.804 to 0.849. The code has been released: [https://github.com/hrlblab/CircleSnake](https://github.com/hrlblab/CircleSnake).

[Download paper here](https://arxiv.org/pdf/2211.01254.pdf)

Recommended citation: Nguyen, E.H., Yang, H., Asad, Z., Deng, R., Fogo, A.B., Huo, Y. (2022). CircleSnake: Instance Segmentation with Circle Representation. In: Lian, C., Cao, X., Rekik, I., Xu, X., Cui, Z. (eds) Machine Learning in Medical Imaging. MLMI 2022. Lecture Notes in Computer Science, vol 13583. Springer, Cham. https://doi.org/10.1007/978-3-031-21014-3_31