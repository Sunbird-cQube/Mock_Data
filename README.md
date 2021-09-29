# cQube Mock_Data
### Initial steps

- Open Terminal

- Navigate to the directory where Mock_Data has been downloaded or cloned
```
cd Mock_Data
git checkout cQube-mockdata
```

### Uploading data to S3 Emission bucket:
- cqube_emission directory available with the below structure.

Master Files:

```
cqube_emission
|
├── school_management_master
│   └── school_management_master.zip
│       └── school_management_master.csv
├── district_master
│   └── district_mst.zip
│       └── district_mst.csv
├── block_master
│   └── block_mst.zip
│       └── block_mst.csv
├── cluster_master
│   └── cluster_mst.zip
│       └── cluster_mst.csv
├── school_master
│   └── school_mst.zip
│       └── school_mst.csv
├── sat
│   └── semester_exam_grade_details.zip
│       └── semester_exam_grade_details.csv
├── sat
│   └── semester_exam_subject_details.zip
│       └── semester_exam_subject_details.csv
├── sat
│   └── semester_exam_mst.zip
│       └── semester_exam_mst.csv
├── sat
│   └── semester_exam_qst_mst.zip
│       └── semester_exam_qst_mst.csv
├── pat
│   └── periodic_exam_grade_details.zip
│       └── periodic_exam_grade_details.csv
├── pat
│   └── periodic_exam_subject_details.zip
│       └── periodic_exam_subject_details.csv
├── pat
│   └── periodic_exam_mst.zip
│       └── periodic_exam_mst.csv
├── pat
│   └── periodic_exam_qst_mst.zip
│       └── periodic_exam_qst_mst.csv

````

Transactional Files:

````
cqube_emission
├── inspection_master
│   └── inspection_master.zip
│       └── inspection_master.csv
├── user_location_master
│   └── user_location_master.zip
│       └── user_location_master.csv
├── infra_trans
│   └── infra_trans.zip
│       └── infra_trans.csv
├── student_attendance
│   └── student_attendance.zip
│       └── student_attendance.csv
├── sat
│   └── semester_exam_result_trans.zip
│       └── semester_exam_result_trans.csv
├── pat
│   └── periodic_exam_result_trans.zip
│       └── periodic_exam_result_trans.csv

````

- Navigate to the ```Scripts``` directory
```
cd Mock_Data/Scripts
```

- Update the emission user details mentioned below in `config.py`.
  - emission access_token 
  - location of the cqube_emission directory where the files are placed as below. Example: `/home/ubuntu/cqube_emission/`
  - emission_url ( `https://<domain_name>/data` Note: URL depends upon the server configured in firewall which includes SSL and reverse proxy location)

- After completing the configuration. Save and close the file.
- Execute the client.py file, as mentioned below to emit the data files to s3_emission bucket. 
```
python3 client.py
```