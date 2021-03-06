
## DICOM RT

Development of DICOM RT Information Objects started in January, 1995
Radiotherapy Information Objects
* RT Structure Set – image segmentation, RT Structure Set, containing information related to patient anatomy, for example structures, markers, and isocenters. These entities are typically identified on devices such as CT scanners, physical or virtual simulation workstations, or treatment planning systems.

* RT Plan – beam/source geometry and dosimetry,  containing geometric and dosimetric data specifying a course of external beam and/or brachytherapy treatment, for example beam angles, collimator openings, beam modifiers, and brachytherapy channel and source specifications. The RT Plan entity may be created by a simulation workstation, and subsequently enriched by a treatment planning system before being passed on to a record and verify system or treatment device. An instance of the RT Plan object usually references a RT Structure Set instance to define a coordinate system and set of patient structures.

* RT Image – projection image in beam geometry,  specifying radiotherapy images which have been obtained on a conical imaging geometry, such as those found on conventional simulators and portal imaging devices. It can also be used for calculated images using the same geometry, such as digitally reconstructed radiographs (DRRs).

* RT Dose – dose matrix and DVHs, containing dose data generated by a treatment planning system in one or more of several formats: three-dimensional dose data, isodose curves, DVHs, or dose points.

#### Radiotherapy Treatment Record (Supp 29, Final Text May 1999)
* RT Beams Treatment Record
* RT Brachy Treatment Record
* RT Treatment Summary Record

Radiotherapy Extensions for Ion Therapy (Supp 102, Final Text Mar 2006)
- RT Ion Plan 
- RT Ion Beams Treatment Record

![DICOM Image with DICOM-RT Extension](https://pubs.rsna.org/cms/10.1148/rg.293075172/asset/images/medium/g09ma01g04x.jpeg)

![DICOM Encoding](https://www.opensource4rt.info/Screen%20shot%202011-10-08%20at%205.05.28%20PM.png)


### tools for DICOM-RT

SlicerRT project in 3D Slicer
https://www.slicer.org/wiki/Documentation/Nightly/Modules/DicomRtImport
DICOM-RT import export (handle datasets of types RT Structure Set, RT Dose, RT Plan, RT Image)
DICOM-SRO import/export (handles DICOM Spatial Registration object, both rigid and deformable)

learn from a package in Matlab ( DICOM-RT to Matlab) https://github.com/ulrikls/dicomrt2matlab
1. Load DICOM headers
2. read contours sequences (reading and converting RT structures) 
Basically in this step, it will load ROINames, Points, VoxelPoints, Segmentation files 
in each slice by looping through contours
3. Save segmentations

####dcmtk-dcmrt, dcmrt - a radiation therapy library and utility apps
This DICOM ToolKit (DCMTK) package consists of source code, documentation and installation instructions for a set of software libraries and applications implementing part of the DICOM/MEDICOM Standard.

### Example of using DCMTK-RT
This example shows how to call C/C++ Library for reading and writing DICOM RT Files. https://github.com/jpneylon/RTClasses

