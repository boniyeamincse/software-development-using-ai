# Module: Medical Imaging & PACS Hub

## Description
The **Picture Archiving and Communication System (PACS)** Hub is a mission-critical module that handles the storage, retrieval, management, and distribution of medical images (DICOM format) such as X-rays, MRIs, and CT scans.

## Business Purpose
Modern medicine is highly clinical-imaging dependent. This module eliminates wait times for physical film, enables remote radiologist reading (teleradiology), and provides doctors with immediate visual context during patient encounters.

## Key Features
* **DICOM Image Server**: High-fidelity storage of medical imaging files.
* **Diagnostic Viewer**: Cloud-native viewer with tools for measurements, overlays, and 3D reconstruction.
* **Radiology Information System (RIS) Link**: Seamless connection between imaging orders and result reports.
* **Collaborative Review**: Multi-user "huddle" rooms for surgical planning.
* **AI-Assisted Screening (Optional)**: Plugin for automated detection of anomalies (e.g., bone fractures).

## User Roles
* **Radiologist**: Primary diagnostic user for reading and reporting.
* **Clinician/Surgeon**: Views images for reference during consultation or surgery.
* **PACS Administrator**: Manages storage infrastructure and DICOM nodes.
* **Patient**: Accesses a low-resolution view of their own images via the portal.

## Workflow
1. **Order**: Clinician creates a "Radiology Order" in the EHR.
2. **Capture**: Technician performs the scan; the machine (Modality) pushes DICOM files to the PACS.
3. **Notify**: Radiologist is alerted to a new "Case" on their worklist.
4. **Diagnosis**: Radiologist opens the viewer, writes the report, and signs off.
5. **Sync**: Report and image links are automatically attached to the Patient’s EHR.

## Database Tables
* `imaging_studies`: Master list of scans performed.
* `dicom_instances`: Registry of individual image files.
* `radiology_reports`: Text-based diagnosis and annotations.
* `modality_nodes`: Configuration for imaging hardware connections.

## API Endpoints
* `GET /api/v1/imaging/studies/{patientId}`: Retrieve clinical image history.
* `POST /api/v1/imaging/upload`: Entry point for modality DICOM streams.
* `GET /api/v1/imaging/view-session`: Generate a secure tokens for the cloud viewer.
* `PUT /api/v1/imaging/reports/{id}`: Submit or update a radiologist's findings.

---
[← Previous: Complete Modules List](16-complete-modules-list.md) | [Back to Index](README.md)
