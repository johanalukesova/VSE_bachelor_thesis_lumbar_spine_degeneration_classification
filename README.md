# Deep Learning in Medical Imaging: Classification of Lumbar Spine Degeneration from MRI Scans
1. First, multiple classification models are compared on a slice-based stenosis classification task. 
2. Second, multiple localization models are compared on a vertebral landmark localization task. 
3. Finally, the best-performing models from both stages are integrated into a complete localization-guided classification pipeline designed for volumetric MRI data. 
    * This final pipeline reflects a realistic clinical workflow, where anatomical structures are first identified and subsequently analyzed for pathological conditions. 
    * The proposed modular pipeline is then compared against both a direct classification baseline and a more integrated reference framework to assess its effectiveness and practical relevance.

The benchmark sections address the following questions:
* Which classification architecture performs best on slice-based lumbar MRI classification?
* Which localization architecture performs best on vertebral landmark detection?

The final pipeline section addresses the following questions:
* Does combining the best-performing localization and classification models produce a clinically useful system?
* How does the modular localization-guided pipeline compare with a stronger integrated reference framework?

### Classification Benchmark
1. VGG
2. ResNet
3. DenseNet
4. EfficientNet
5. Vision Transformer (ViT)
6. Swin Transformer

### Localization Benchmark
* U-Net
* Attention U-Net
* ViT-UNet
* UNETR
* Swin-UNet

## Datasets used: 
* Spider dataset:
    * https://spider.grand-challenge.org/data/

* Coordinate Pretraining Dataset for Kaggle competition:
    * https://www.kaggle.com/competitions/rsna-2024-lumbar-spine-degenerative-classification


## Kaggle competition: Classify lumbar spine degenerative conditions
### Description 
* Low back pain is the leading cause of disability worldwide, according to the World Health Organization, affecting 619 million people in 2020. Most people experience low back pain at some point in their lives, with the frequency increasing with age. Pain and restricted mobility are often symptoms of spondylosis, a set of degenerative spine conditions including degeneration of intervertebral discs and subsequent narrowing of the spinal canal (spinal stenosis), subarticular recesses, or neural foramen with associated compression or irritations of the nerves in the low back.

* Magnetic resonance imaging (MRI) provides a detailed view of the lumbar spine vertebra, discs and nerves, enabling radiologists to assess the presence and severity of these conditions. Proper diagnosis and grading of these conditions help guide treatment and potential surgery to help alleviate back pain and improve overall health and quality of life for patients.

* RSNA has teamed with the American Society of Neuroradiology (ASNR) to conduct this competition exploring whether artificial intelligence can be used to aid in the detection and classification of degenerative spine conditions using lumbar spine MR images.

* The challenge will focus on the classification of five lumbar spine degenerative conditions: Left Neural Foraminal Narrowing, Right Neural Foraminal Narrowing, Left Subarticular Stenosis, Right Subarticular Stenosis, and Spinal Canal Stenosis. For each imaging study in the dataset, we’ve provided severity scores (Normal/Mild, Moderate, or Severe) for each of the five conditions across the intervertebral disc levels L1/L2, L2/L3, L3/L4, L4/L5, and L5/S1.

### Goal 
The goal of this competition is to create models that can be used to aid in the detection and classification of degenerative spine conditions using lumbar spine MR images. Competitors will develop models that simulate a radiologist's performance in diagnosing spine conditions.

## Lumbar spine anatomy 
The lumbar spine consists of five vertebrae (L1 to L5) located between the thoracic spine and the sacrum. 
These vertebrae are the largest and strongest in the spine, reflecting their role in supporting much of the body's weight and providing stability and flexibility.

### Lumbar vertebrae

* **Vertebral Bodies** - serve as the primary weight-bearing structures of the spine. Between each pair of vertebral bodies lies an intervertebral disc, which acts as a cushion and allows for movement between the vertebrae.
* **Intervertebral Discs** - composed of a tough outer layer called the annulus fibrosus and a gel-like core called the nucleus pulposus which together act as shock absorbers.
* **Vertebral Arch** - forms the back (posterior) part of the vertebra and surrounds the spinal canal. It consists of **pedicles**: short, thick processes that connect the vertebral body to the transverse processes and **laminae**: Flat plates of bone that extend from the pedicles and meet at the midline to form the back of the vertebral arch.
* **Spinous and Transverse Processes** - These processes serve as attachment points for muscles and ligaments and also play a role in the leverage and movement of the spine.
* **Facet Joints** - Each vertebra has four facet joints which guide and limit the range of motion of the spine.
* **Vertebral Foramina** - openings located on the sides of the vertebrae, 
* **Spinal Canal** (and Spinal Cord) - The spinal canal is the hollow passage that runs vertically through the vertebrae, formed by the alignment of the vertebral foramina. It houses and protects the spinal cord and the nerve roots as they extend down the spine.


### Vertebrae ligaments 

1. Anterior Longitudinal Ligament (ALL): Runs along the front of the vertebral bodies and discs.
2. Posterior Longitudinal Ligament (PLL): Runs along the back of the vertebral bodies inside the spinal canal.
3. Ligamentum Flavum: Connects the laminae of adjacent vertebrae and has an elastic quality.

## Spinal stenosis 
Stenosis refers to the pathological narrowing of a bodily passage or channel. In the context of the spine, particularly the lumbar region, stenosis describes the reduction in the space within the spinal canal, neural foramina, or subarticular recesses, which are essential pathways for the spinal cord and nerve roots. This narrowing can result from various degenerative changes, including hypertrophy of the facet joints, bulging of intervertebral discs, or thickening of the ligaments, such as the ligamentum flavum.


###  Types of stenosis
There are three different types of spinal stenosis: foraminal, central, and lateral. All three consist of narrowing in spine but more specifically are in different regions of your spinal canal.
1. Lateral - nerve is pinched as it exists the spinal canal.
2. Central - nerve is pinched in the main spinal canal.
3. Foraminal - nerve is pinched in the passageways located on each side of vertebrea.

