# RSNA 2024 Lumbar Spine Degenerative Classification
## Kaggle competition: Classify lumbar spine degenerative conditions
### Description 
* Low back pain is the leading cause of disability worldwide, according to the World Health Organization, affecting 619 million people in 2020. Most people experience low back pain at some point in their lives, with the frequency increasing with age. Pain and restricted mobility are often symptoms of spondylosis, a set of degenerative spine conditions including degeneration of intervertebral discs and subsequent narrowing of the spinal canal (spinal stenosis), subarticular recesses, or neural foramen with associated compression or irritations of the nerves in the low back.

* Magnetic resonance imaging (MRI) provides a detailed view of the lumbar spine vertebra, discs and nerves, enabling radiologists to assess the presence and severity of these conditions. Proper diagnosis and grading of these conditions help guide treatment and potential surgery to help alleviate back pain and improve overall health and quality of life for patients.

* RSNA has teamed with the American Society of Neuroradiology (ASNR) to conduct this competition exploring whether artificial intelligence can be used to aid in the detection and classification of degenerative spine conditions using lumbar spine MR images.

* The challenge will focus on the classification of five lumbar spine degenerative conditions: Left Neural Foraminal Narrowing, Right Neural Foraminal Narrowing, Left Subarticular Stenosis, Right Subarticular Stenosis, and Spinal Canal Stenosis. For each imaging study in the dataset, we’ve provided severity scores (Normal/Mild, Moderate, or Severe) for each of the five conditions across the intervertebral disc levels L1/L2, L2/L3, L3/L4, L4/L5, and L5/S1.

# Theoretical part
To build a neural network for lumbar spine degenerative classification, it's essential to have a solid understanding of lumbar spine anatomy and how these structures appear on MRI.

<div>
<img src="attachment:527f788f-1299-4778-93b7-07f9ba97ba0d.jpg" width="400"/>

## Spinal stenosis 
Stenosis refers to the pathological narrowing of a bodily passage or channel. In the context of the spine, particularly the lumbar region, stenosis describes the reduction in the space within the spinal canal, neural foramina, or subarticular recesses, which are essential pathways for the spinal cord and nerve roots. This narrowing can result from various degenerative changes, including hypertrophy of the facet joints, bulging of intervertebral discs, or thickening of the ligaments, such as the ligamentum flavum.


![Stenosis-Types.jpg](attachment:8029a70b-51e6-4a2c-8aa9-2ff06ea30e09.jpg)
1. Lateral - nerve is pinched as it exists the spinal canal.
2. Central - nerve is pinched in the main spinal canal.
3. Foraminal - nerve is pinched in the passageways located on each side of vertebrea.

![7905-241447-2x.jpg](attachment:dc2e1fd9-8983-41f8-bbcb-df16042e5d51.jpg)

## MRI imaging 
Magnetic resonance imaging (MRI) is a medical imaging technique used in radiology to form pictures of the anatomy and the physiological processes inside the body. MRI scanners use strong magnetic fields, magnetic field gradients, and radio waves to generate images of the organs in the body. MRI does not involve X-rays or the use of ionizing radiation, which distinguishes it from computed tomography (CT) and positron emission tomography (PET) scans. 

When imaging the lumbar spine, MRI is particularly valuable because it provides detailed images of both bone structures (vertebrae) and soft tissues (intervertebral discs, spinal cord, nerve roots, ligaments, and muscles). This is essential for diagnosing conditions like spinal stenosis.

### MRI planes 
There are three distinct orientations through whichMRI scans can be interpreted, namely sagittal, axial, and coronal.These different planes allow radiologists to examine anatomical structures from multiple perspectives, aiding in more accurate diagnosis and treatment planning.
* Axial Plane: Horizontal slices, top to bottom view.
* Sagittal Plane: Vertical slices, side to side view.
* Coronal Plane: Vertical slices, front to back view.

<div>
<img src="attachment:2b3f6b04-f9cc-40fb-bf7e-c06509ca613e.jpg" width="500"/>
</div>


### Image types 
* **T1-Weighted Images:** These images provide good anatomical detail and are useful for viewing the structure of the vertebrae and the presence of fat. T1 images show fat as bright and water as dark.
* **T2-Weighted Images:** These are particularly useful for detecting pathological changes, as they highlight differences in water content. T2 images show fluid (like cerebrospinal fluid) as bright and are excellent for visualizing the intervertebral discs and identifying abnormalities such as herniations or inflammation.
* **STIR (Short Tau Inversion Recovery):** A type of T2-weighted imaging that is particularly sensitive to changes in water content, making it useful for detecting inflammation or edema in soft tissues.

<div>
<img src="attachment:11fd76b2-4a08-46e2-9317-9eb00223c222.jpg" width="500"/>
</div>

### Spinal stenosis grading 
1. **Spinal Canal Stenosis:** is characterized by the narrowing of the spinal canal, which can be caused by a combination of factors, including disc bulging, ligamentum flavum thickening, and facet hypertrophy. It is best assessed on sagittal and axial T2-weighted images.
2. **Neural Foraminal Narrowing:** is typically assessed in axial and sagittal views. It appears as a reduction in the space where the nerve roots exit, often caused by disc bulges, osteophytes, or ligament thickening.

<div>
<img src="attachment:66f3a3d8-ae06-4d59-838a-019026c4d2bc.jpeg" width="700"/>
</div>

### MRI Images 
* **DICOM** (Digital Imaging and Communications in Medicine) is an international standard for storing, transmitting, and sharing medical images and associated data. It is widely used in the field of medical imaging to ensure that images from devices, such as MRI can be consistently formatted and shared across various platforms and institutions.
* **Instance number** in our dataset then indicates its position as a slice in the series of one MRI imaging.
* Working with DICOM files in Python can be efficiently managed using library **pydicom**, which provides a simple interface for reading, modifying, and writing DICOM files.
<div>
<img src="attachment:c6ad30c5-86ad-408e-8c82-532eb5384bb5.png" width="600"/>
</div>

### Kaggle data format
<div>
<img src="attachment:0d54a2b4-46d7-42c4-afdc-d7ca1310be92.png" width="700"/>
</div>
