---
author-meta:
- Riqiang Gao
- Mirza S. Khan
bibliography:
- content/manual-references.json
date-meta: '2020-05-16'
header-includes: '<!--

  Manubot generated metadata rendered from header-includes-template.html.

  Suggest improvements at https://github.com/manubot/manubot/blob/master/manubot/process/header-includes-template.html

  -->

  <meta name="dc.format" content="text/html" />

  <meta name="dc.title" content="Python-based Quality Assessment Tools for Medical Imaging" />

  <meta name="citation_title" content="Python-based Quality Assessment Tools for Medical Imaging" />

  <meta property="og:title" content="Python-based Quality Assessment Tools for Medical Imaging" />

  <meta property="twitter:title" content="Python-based Quality Assessment Tools for Medical Imaging" />

  <meta name="dc.date" content="2020-05-16" />

  <meta name="citation_publication_date" content="2020-05-16" />

  <meta name="dc.language" content="en-US" />

  <meta name="citation_language" content="en-US" />

  <meta name="dc.relation.ispartof" content="Manubot" />

  <meta name="dc.publisher" content="Manubot" />

  <meta name="citation_journal_title" content="Manubot" />

  <meta name="citation_technical_report_institution" content="Manubot" />

  <meta name="citation_author" content="Riqiang Gao" />

  <meta name="citation_author_institution" content="Electrical Engineering and Computer Science, Vanderbilt University" />

  <meta name="citation_author_orcid" content="XXXX-XXXX-XXXX-XXXX" />

  <meta name="twitter:creator" content="@johndoe" />

  <meta name="citation_author" content="Mirza S. Khan" />

  <meta name="citation_author_institution" content="U.S. Department of Veterans Affairs, Tennessee Valley Healthcare System" />

  <meta name="citation_author_institution" content="Department of Biomedical Informatics, Vanderbilt University" />

  <meta name="citation_author_orcid" content="0000-0001-7007-9437" />

  <link rel="canonical" href="https://mirzask.github.io/QA_paper/" />

  <meta property="og:url" content="https://mirzask.github.io/QA_paper/" />

  <meta property="twitter:url" content="https://mirzask.github.io/QA_paper/" />

  <meta name="citation_fulltext_html_url" content="https://mirzask.github.io/QA_paper/" />

  <meta name="citation_pdf_url" content="https://mirzask.github.io/QA_paper/manuscript.pdf" />

  <link rel="alternate" type="application/pdf" href="https://mirzask.github.io/QA_paper/manuscript.pdf" />

  <link rel="alternate" type="text/html" href="https://mirzask.github.io/QA_paper/v/b55609c75aaacbb2093ae30e4b74eb736fe89ba2/" />

  <meta name="manubot_html_url_versioned" content="https://mirzask.github.io/QA_paper/v/b55609c75aaacbb2093ae30e4b74eb736fe89ba2/" />

  <meta name="manubot_pdf_url_versioned" content="https://mirzask.github.io/QA_paper/v/b55609c75aaacbb2093ae30e4b74eb736fe89ba2/manuscript.pdf" />

  <meta property="og:type" content="article" />

  <meta property="twitter:card" content="summary_large_image" />

  <link rel="icon" type="image/png" sizes="192x192" href="https://manubot.org/favicon-192x192.png" />

  <link rel="mask-icon" href="https://manubot.org/safari-pinned-tab.svg" color="#ad1457" />

  <meta name="theme-color" content="#ad1457" />

  <!-- end Manubot generated metadata -->'
keywords:
- quality assessment
- medical imaging
- DICOM
- NifTI
lang: en-US
manubot-clear-requests-cache: false
manubot-output-bibliography: output/references.json
manubot-output-citekeys: output/citations.tsv
manubot-requests-cache-path: ci/cache/requests-cache
title: Python-based Quality Assessment Tools for Medical Imaging
...






<small><em>
This manuscript
([permalink](https://mirzask.github.io/QA_paper/v/b55609c75aaacbb2093ae30e4b74eb736fe89ba2/))
was automatically generated
from [mirzask/QA_paper@b55609c](https://github.com/mirzask/QA_paper/tree/b55609c75aaacbb2093ae30e4b74eb736fe89ba2)
on May 16, 2020.
</em></small>

## Authors



+ **Riqiang Gao**<br>
    ![ORCID icon](images/orcid.svg){.inline_icon}
    [XXXX-XXXX-XXXX-XXXX](https://orcid.org/XXXX-XXXX-XXXX-XXXX)
    · ![GitHub icon](images/github.svg){.inline_icon}
    [RiqiangGao](https://github.com/RiqiangGao)
    · ![Twitter icon](images/twitter.svg){.inline_icon}
    [johndoe](https://twitter.com/johndoe)<br>
  <small>
     Electrical Engineering and Computer Science, Vanderbilt University
     · Funded by Grant XXXXXXXX
  </small>

+ **Mirza S. Khan**<br>
    ![ORCID icon](images/orcid.svg){.inline_icon}
    [0000-0001-7007-9437](https://orcid.org/0000-0001-7007-9437)
    · ![GitHub icon](images/github.svg){.inline_icon}
    [mirzask](https://github.com/mirzask)<br>
  <small>
     U.S. Department of Veterans Affairs, Tennessee Valley Healthcare System; Department of Biomedical Informatics, Vanderbilt University
  </small>



## Abstract {.page_break_before}


Ensuring good quality of medical images (e.g., computed tomography, CT) is essential for achieve maximum diagnostic information and image interpretation. While in practice, medical imaging can be destroyed by many factors such as system error at data acquisition and network transferring. Multiple existed tools are developed to deal with medical imaging, while most of them are either fail to handle multiple errors may encounter or provide comprehensive quality assessment (QA) report. In this paper, we develop a whole pipeline with several open source applications to assess the quality of CT images from the original DICOM file, and convert to 3D NIFTI files. Seven possible steps are checked to make sure the medical images are appropriate for next steps (diagnostic usage or machine learning). Our QA tool has been proved to be useful and time-saving for clinical laboratory usage and processing data for image interpretation.

The code and tutorials are publicly available at https://github.com/MASILab/QA_tool.


## Introduction {.page_break_before}

The primary use case for medical imaging is for interpretation by radiologists and other trained persons. Secondary use of medical imaging for research and discovery has become more prominent and has led to many meaningful contributions to imaging and medicine. 

Often, analyses relying on medical imaging utilize the raw Digital Imaging and Communications in Medicine (DICOM) image files or other common image file formats, such as nrrd or NIfTI. In medical image de-identification, minor encoding errors or manipulation of DICOM file data could render these files useless or inaccessible [**citation**]. On a similar note, adjustments/modifications to image files, such as those used to aid a radiologists' view, may pose challenges for image modeling tasks. Yet, ~~there remains little consensus or tools providing a pipeline~~ little attention has been afforded to ensure the quality of medical image files prior to use in model training ~~to be used in downstream analyses~~.

Data quality is often an under-appreciated but vital component for machine learning tasks, including natural language processing and computer vision. This is often described by the adage, "garbage in, garbage out." In order to address this matter for our own model development, we have developed a series of sensible, automated data quality checks for medical imaging data.

Here we present our tool to assist with quality assessment of medical image files... We demonstrate its use on NLST and x other imaging studies... (some NLST image files are of poor quality; how does this affect model performance?). Demonstrate improved performance of downstream learning tasks by using satisfactory images for training.


## Intuition and Task Description

In this paper, we describe the several steps of quality assessment (QA) for the de-identified CT scans, including the steps converting 2D DICOM files to 3D NIFTI.

## Related Tools used in our Pipeline

## Detailed Steps

### Instance Number Checking

*Instance Number (IN)* is a number that identifies this image in DICOM files, which was named Image Number in earlier versions [1]. Generally, the INs of DICOM images in a single scan should be a series of consecutive integers. Our first priority is to check if there are any missing INs of the CT scan. We check the IN using

$$
\begin{array}{c}
C_{1}=\max \left\{i n_{i}\right\}-\min \left\{i n_{i}\right\}+1-\text {size}\left\{i n_{i}\right\} \\
\left.C_{2}=\sum_{i, j, i < j} 1\left\{i n_{i}=i n_j\right\}\right\}
\end{array}
$$

where $\{i n_{i}\}$ is the list of INs of the DICOM files, and $\text {size}\left\{i n_{i}\right\}$ indicates how many DICOMs in the scan. $C_1$ and $C_2$ represent how many slices are missed in the scan and how many slice-pairs with the same IN, respectively. The CT scan passes the Instance Number check if $C_1=0$ and $C_2=0$.


### Slice Distance Checking

*Slice Location* is defined as the relative position of the image plane expressed in mm. This information is relative to an unspecified implementation specific reference point [@url:https://dicom.innolitics.com/ciods/ct-image/image-plane/00201041]. Slice Distance (SD) is defined as subtraction of Slice Location of the two consecutive DICOMs. Generally speaking, the SD of all consecutive pairs should be the same in a scan, while in practice, the system error might result in very small difference. Herein, we introduce a self-defined threshold to tolerant the system error. The SD checking is

$$
C_{3}=\sum_{i} 1\left\{s d_{i}<\varepsilon\right\}
$$

where $\{ sd_i \}$ is the list of SDs of DICOM files, is the self-defined tolerance threshold. $C_3$ represents how many places which slice distance error. The CT scan pass the Instance Number checking if $C_3=0$.

### Filtering Scans with few slices

Some scans with unreasonable limited number of slices but can easily pass the Instance Number checking and Slice Distance checking. For example, if a chest scan only with 3 DICOM slices, it cannot be usable. Filtering those scans can be easily done with a self-defined threshold on $\text {size}\left\{i n_{i}\right\}$.


$$
C_4 = 1 \{ \text {size}\left\{i n_{i}\right\} < \delta \}
$$

where $\delta$ is the self-defined threshold for filtering scans with few slices. The CT scan pass the filtering checking if $C_4=0$.

### Physical Length Filtering

Some scans are unreasonable extended out of the Region of Interest. For example, the target scan is chest CT while is given a whole-body scan. Another situation is only a chunk of chest CT is given without a complete lung. The *Physical Length Filtering* is designed for selecting those CTs with unreasonable physical body length for further processing or removing. Two thresholds are needed (i.e., low bound and upper bound of physical body length) for filtering

$$
C_5 = 1 \{ \sigma_1 < PL < \sigma_2 \}
$$

where $PL$ is the physical length computed from Slice Location of DICOMs, $\sigma_1$ and $\sigma_2$ are the self-defined low bound and upper bound. The CT scan pass the filtering checking if $C_5=1$.

### Convert DICOM files to NifTI

We use an open-source tool `dcm2niix` [@doi:10.1016/j.jneumeth.2016.03.001] to convert DICOMs file to NIFTI.

### NifTI orientation Check and Resolution filtering

We check the CT orientation and resolution in the affine matrix A, whose size is 4x4. We have

$$
\begin{array}{c}
C_{6}=1\left\{-A_{11}=A_{22}=A_{33}>0\right\} \\
C_{7}=\sum_{i=1}^{3} 1\left\{\left|A_{i i}\right|>\Phi_{i}\right\}
\end{array}
$$

where $\Phi$ is the thresholds of 3 dimensions. The CT scan is not with standard orientation if $C_6=0$, and we use the open source `fslreorient2std` to convert CT to standard orientation. $C_7>0$ represents that the CT does not match resolution requirements.

### Double check with visualized slices

We use the `slicesdir` [**citation**] to visualize scans.

## Methods



## Results

![Case of Instance Number check failure.](https://raw.githubusercontent.com/MASILab/QA_tool/master/example_image/InstanceCheck.png){#fig:instance-check}

![Case of Slice Distance check failure.](https://raw.githubusercontent.com/MASILab/QA_tool/master/example_image/SliceDistance.png){#fig:slice-distance}

![Case of Filtering too few slices.](https://raw.githubusercontent.com/MASILab/QA_tool/master/example_image/FewSlices.png){#fig:few-slices}

![Case of Physical Length Filtering showing extension outside of the region of interest.](https://raw.githubusercontent.com/MASILab/QA_tool/master/example_image/PhysicalLength.png)

![Case of Orientation check failure.](https://raw.githubusercontent.com/MASILab/QA_tool/master/example_image/orientationCheck.png)

![Case found in `slicesdir` sanity check failure.](https://raw.githubusercontent.com/MASILab/QA_tool/master/example_image/slicesdirCheck.png)

## References {.page_break_before}

<!-- Explicitly insert bibliography here -->
<div id="refs"></div>
