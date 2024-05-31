# Hospital **DBMS**

## Introduction

This system is designed for use strictly by the employees of a
hospital network. The network includes several segments. 
The database system should be able to query basic information about the hospital employees such as staff ID number, name, address, and phone number etc. The system should be able to query information about room and patient assignments for each employee of a department. Data can be fetched by various ways, due to some rules applied on database elements.

## Facts and figures  

> I) This is a real life Database example, containing all real data:

- **CNIC:** is according to these rules that are applied on the basis of which Pakistan's CNIC numbers are allocated;
  1)  Provinces codes at start

| Province    | Code | 
|-------------|----------|
| Punjab       | 1   | 
| Sindh       | 2   | 
| KPK       | 3  | 
| Balochistan       | 4   | 
| AJ & Kashmir       | 5  | 
| Gilgit-Baltistan       | 6   | 
| FATA       | 7   | 

2) Gender specifing code at last

| Gender       | Code   | 
|-------------|----------|
| Male      |  5   | 
| Female       | 4   | 

> II) The real names are used.  

>III) The addresses used exist in real life.

> IV) There is the connection build between the entities.

## Data Dictionery

This is the complete data dictionery used in code:

![DD1](/Database%20images/Capture1.PNG)  
![DD1](/Database%20images/Capture2.PNG)   
![DD1](/Database%20images/Capture3.PNG) 

## ERD

![DD1](/Database%20images/ERD.PNG) 

SQL code 

```SQL
DROP DATABASE IF EXISTS Hospital_database_system;
create database Hospital_database_system
-- Patient table
DROP TABLE IF EXISTS patient;
CREATE TABLE patient (
 patient_id VARCHAR(50) PRIMARY KEY,
 patient_name NVARCHAR(200) Not Null,
 patient_age INT Not Null,
 patient_gender VARCHAR(10) Not Null,
 patient_cnic VARCHAR(15) Unique,
 patient_contact VARCHAR(20) Not Null,
 patient_address NVARCHAR(1000) Not Null
);
-- Inserting data 
INSERT INTO patient (patient_id, patient_name, patient_age, patient_gender, patient_cnic, 
patient_contact, patient_address)
VALUES ('pat3_01', 'Ali Khan', 25, 'Male', '35201-6789012-3', '0312-1234567', '22B Gulberg III, Lahore, 
Pakistan'),
('pat2_02', 'Aisha Ahmed', 30, 'Female', '65201-7890123-4', '0321-2345678', 'House No. 5, Street 10, F7/2, Islamabad, Pakistan'),
('pat3_03', 'Imran Malik', 32, 'Male', '44567-8901234-5', '0333-3456789', '15 Green Town, Phase 2, 
Karachi, Pakistan'),
('pat2_04', 'Saima Khan', 28, 'Female', '35678-9012345-6', '0344-4567890', '7C Model Town Extension, 
Multan, Pakistan'),
('pat3_05', 'Tariq Mahmood', 35, 'Male', '36789-0123456-7', '0315-5678901', 'Apartment #302, Liberty 
Market Tower, Faisalabad, Pakistan'),
('pat2_06', 'Sadia Farooq', 27, 'Female', '67890-1234567-8', '0324-6789012', '33 Canal Road, G-10/4, 
Islamabad, Pakistan'),
('pat3_07', 'Fahad Ali', 40, 'Male', '38901-2345678-9', '0336-7890123', '18 Mall Road, Lahore Cantt, 
Lahore, Pakistan'),
('pat2_08', 'Nadia Riaz', 29, 'Female', '49012-3456789-0', '0347-8901234', 'House No. 12, Block 5, Clifton, 
Karachi, Pakistan'),
('pat3_09', 'Zahid Iqbal', 31, 'Male', '40123-4567890-1', '0318-9012345', '25 Gulshan-e-Iqbal, Block 10-A, 
Karachi, Pakistan'),
('pat3_10', 'Rukhsar Malik', 26, 'Male', '31234-5678901-2', '0327-0123456', '9A Satellite Town, 
Rawalpindi, Pakistan'),
('pat3_11', 'Ahmed Khan', 33, 'Male', '38765-4321798-7', '0330-1234567', '6C Civil Lines, Bahawalpur, 
Pakistan'),
('pat2_12', 'Nazia Akhtar', 28, 'Female', '37654-3110987-6', '0341-2345678', 'Flat #8, Al-Hafeez Heights, 
Main Boulevard, Gulberg III, Lahore, Pakistan'),
('pat3_13', 'Adeel Ahmed', 35, 'Male', '36543-2100876-5', '0313-3456789', '3D Phase 1, DHA, Lahore, 
Pakistan'),
('pat2_14', 'Sana Jamil', 29, 'Female', '15432-1098765-4', '0322-4567890', '14B University Road, 
Peshawar, Pakistan'),
('pat3_15', 'Waqar Ali', 30, 'Male', '64321-0987654-3', '0333-5678901', 'House No. 7, Street 4, F-10/3, 
Islamabad, Pakistan'),
('pat2_16', 'Hira Riaz', 31, 'Female', '43210-9876543-2', '0344-6789012', '21 Defence Housing Authority, 
Phase 5, Karachi, Pakistan'),
('pat3_17', 'Usman Malik', 32, 'Male', '32109-8765432-1', '0315-7890123', 'Apartment #17, Hill View 
Apartments, Murree Road, Rawalpindi, Pakistan'),
('pat2_18', 'Ayesha Anwar', 28, 'Female', '31098-7654321-0', '0324-8901234', '10B Jail Road, Lahore, 
Pakistan'),
('pat3_19', 'Bilal Iqbal', 33, 'Male', '30987-6543210-9', '0336-9012345', '8E Model Colony, Lahore, 
Pakistan'),
('pat2_20', 'Rabia Ahmed', 29, 'Female', '69876-5432109-8', '0347-0123456', 'House No. 3, Street 12, G6/3, Islamabad, Pakistan'),
('pat2_21', 'Amna Khalid', 34, 'Female', '38765-4321098-7', '0318-1234567', '45A Commercial Area, 
Phase 3, DHA, Lahore, Pakistan'),
('pat3_22', 'Faisal Ali', 27, 'Male', '37654-3210987-6', '0327-2345678', '2C Satellite Town, Gujranwala, 
Pakistan'),
('pat2_23', 'Nida Rehman', 36, 'Female', '36543-2109876-5', '0330-3456789', '11 Shadman, Block A, 
Lahore, Pakistan'),
('pat3_24', 'Ahmed Hassan', 28, 'Male', '45432-1098765-4', '0341-4567890', 'Apartment #6, City Tower, 
Shahrah-e-Faisal, Karachi, Pakistan'),
('pat2_25', 'Saba Imran', 29, 'Female', '44321-0987654-3', '0313-5678901', '29 Defence View, Phase 2, 
Karachi, Pakistan'),
('pat3_26', 'Haris Ahmed', 30, 'Male', '63210-9876543-2', '0322-6789012', 'House No. 17, Street 7, G-9/1, 
Islamabad, Pakistan'),
('pat2_27', 'Asma Khan', 31, 'Female', '42109-8765432-1', '0333-7890123', '5B Cantt Area, Hyderabad, 
Pakistan'),
('pat3_28', 'Jawad Malik', 32, 'Male', '31098-7654331-0', '0344-8901234', '16A Johar Town, Lahore, 
Pakistan'),
('pat2_29', 'Shabnam Akhtar', 28, 'Female', '50987-6543210-9', '0315-9012345', '22 Stadium Road, 
Quetta, Pakistan'),
('pat3_30', 'Talha Iqbal', 31, 'Male', '39876-5432109-8', '0324-0123456', 'House No. 9, Block 3, Model 
Town, Lahore, Pakistan');
-- Tool_machinery table
DROP TABLE IF EXISTS tool_machinery;
CREATE TABLE tool_machinery (
 tool_machinery_id VARCHAR(10) PRIMARY KEY,
 tool_machinery_name NVARCHAR(255) Not Null
);
-- Insert data 
INSERT INTO tool_machinery (tool_machinery_id, tool_machinery_name) 
VALUES
('tm_01', 'X-Ray Machine'),
('tm_02', 'Ultrasound Scanner'),
('tm_03', 'MRI Machine'),
('tm_04', 'CT Scan Machine'),
('tm_05', 'Blood Pressure Monitor'),
('tm_06', 'Oxygen Concentrator'),
('tm_07', 'Defibrillator'),
('tm_08', 'Surgical Tools Set'),
('tm_09', 'Sterilization Equipment'),
('tm_10', 'Anesthesia Machine'),
('tm_11', 'Endoscopy Equipment'),
('tm_12', 'Electrocardiogram (ECG) Machine'),
('tm_13', 'Ventilator'),
('tm_14', 'Patient Monitoring System'),
('tm_15', 'Dental Chair'),
('tm_16', 'Laboratory Centrifuge'),
('tm_17', 'Autoclave'),
('tm_18', 'Suction Machine'),
('tm_19', 'Wheelchair'),
('tm_20', 'Surgical Lights'),
('tm_21', 'Incubator'),
('tm_22', 'Dialysis Machine'),
('tm_23', 'Operating Table'),
('tm_24', 'C-Arm Fluoroscopy Machine'),
('tm_25', 'Crash Cart'),
('tm_26', 'Nebulizer'),
('tm_27', 'Infusion Pump'),
('tm_28', 'Stethoscope'),
('tm_29', 'Electrosurgical Unit'),
('tm_30', 'Patient Bed');
-- Staff table
DROP TABLE IF EXISTS staff;
CREATE TABLE staff (
 staff_id VARCHAR(10) PRIMARY KEY,
 staff_name NVARCHAR(255) Not Null,
 staff_age INT Not Null,
 staff_phonenumber VARCHAR(20) Not Null,
 staff_salary DECIMAL(10, 2) Not Null,
 staff_address NVARCHAR(255) Not Null,
 staff_gender VARCHAR(10) Not Null,
 staff_cnic VARCHAR(15) Unique
);
-- Inserting data 
INSERT INTO staff (staff_id, staff_name, staff_age, staff_phonenumber, staff_salary, staff_address, 
staff_gender, staff_cnic)
VALUES
('stf3_01', 'Muhammad Ali', 28, '0312-3456789', 50000.00, '123 Main Street, Karachi', 'Male', '42345-
6789012-3'),
('stf2_02', 'Aisha Ahmed', 35, '0321-4567890', 60000.00, '456 Business Road, Lahore', 'Female', '33456-
7890123-4'),
('stf3_03', 'Imran Khan', 42, '0333-5678901', 70000.00, '789 Corporate Lane, Islamabad', 'Male', '64567-
8901234-5'),
('stf2_04', 'Sana Farooq', 30, '0344-6789012', 55000.00, '101 Commercial Avenue, Multan', 'Female', 
'35678-9012345-6'),
('stf3_05', 'Tariq Wilson', 37, '0315-7890123', 65000.00, '202 Industrial Plaza, Quetta', 'Male', '16789-
0123456-7'),
('stf2_06', 'Ayesha Riaz', 29, '0324-8901234', 52000.00 , '303 Business Center, Sialkot', 'Female', '37890-
1234567-8'),
('stf3_07', 'Zain Malik', 33, '0336-9012345', 60000.00, '404 Corporate Hub, Rawalpindi', 'Male', '38901-
2345678-9'),
('stf2_08', 'Noor Brown', 38, '0347-0123456', 75000.00, '505 Commercial Street, Faisalabad', 'Female', 
'39012-3456789-0'),
('stf3_09', 'Usman Taylor', 31, '0318-1234567', 58000.00, '606 Business Complex, Lahore', 'Male', 
'30123-4567890-1'),
('stf2_10', 'Saima batool', 36, '0327-2345678', 68000.00, '707 Corporate Tower, Karachi', 'Female', 
'41234-5678901-2'),
('stf3_11', 'Ahmed Khan', 27, '0330-3456789', 48000.00, '808 Industrial Lane, Peshawar', 'Male', '38765-
4321098-7'),
('stf2_12', 'Nazia Akhtar', 34, '0341-4567890', 67000.00, '909 Business Avenue, Gujranwala', 'Female', 
'37654-3210987-6'),
('stf3_13', 'Bilal Iqbal', 32, '0313-5678901', 59000.00, '101 Commercial Road, Quetta', 'Male', '16543-
2109876-5'),
('stf2_14', 'Sana Jamil', 29, '0322-6789012', 52000.00, '202 Industrial Street, Sahiwal', 'Female', '35432-
1098765-4'),
('stf3_15', 'Waqar Ali', 35, '0333-7890123', 70000.00, '303 Business Lane, Multan', 'Male', '34321-
0987654-3'),
('stf2_16', 'Hira Riaz', 30, '0344-8901234', 55000.00, '404 Corporate Plaza, Okara', 'Female', '33210-
9876543-2'),
('stf3_17', 'Usman Malik', 39, '0315-0123456', 72000.00, '505 Commercial Road, Rawalpindi', 'Male', 
'32109-8765432-1'),
('stf2_18', 'Ayesha Anwar', 28, '0324-2345678', 53000.00, '606 Business Street, Islamabad', 'Female', 
'61098-7654321-0'),
('stf3_19', 'Faisal Ali', 32, '0336-3456789', 59000.00, '707 Corporate Road, Lahore', 'Male', '30987-
6543210-9'),
('stf2_20', 'Nida Rehman', 37, '0347-4567890', 67000.00, '808 Industrial Avenue, Karachi', 'Female', 
'49876-5432109-8');
-- Rooms table
DROP TABLE IF EXISTS rooms;
CREATE TABLE rooms (
 room_no VARCHAR(10) PRIMARY KEY,
 tool_machinery_id VARCHAR(10) REFERENCES tool_machinery(tool_machinery_id)
);
-- Insert data for rooms
INSERT INTO rooms (room_no, tool_machinery_id) VALUES
('Rm_01', 'tm_01'),
('Rm_02', 'tm_02'),
('Rm_03', 'tm_03'),
('Rm_04', 'tm_04'),
('Rm_05', 'tm_05'),
('Rm_06', 'tm_06'),
('Rm_07', 'tm_07'),
('Rm_08', 'tm_08'),
('Rm_09', 'tm_09'),
('Rm_10', 'tm_10'),
('Rm_11', 'tm_11'),
('Rm_12', 'tm_12'),
('Rm_13', 'tm_13'),
('Rm_14', 'tm_14'),
('Rm_15', 'tm_15'),
('Rm_16', 'tm_16'),
('Rm_17', 'tm_17'),
('Rm_18', 'tm_18'),
('Rm_19', 'tm_19'),
('Rm_20', 'tm_20'),
('Rm_21', 'tm_21'),
('Rm_22', 'tm_22'),
('Rm_23', 'tm_23'),
('Rm_24', 'tm_24'),
('Rm_25', 'tm_25'),
('Rm_26', 'tm_26'),
('Rm_27', 'tm_27'),
('Rm_28', 'tm_28'),
('Rm_29', 'tm_29'),
('Rm_30', 'tm_30'),
('Rm_31', 'tm_01'),
('Rm_32', 'tm_02'),
('Rm_33', 'tm_03'),
('Rm_34', 'tm_04'),
('Rm_35', 'tm_05'),
('Rm_36', 'tm_06'),
('Rm_37', 'tm_07'),
('Rm_38', 'tm_08'),
('Rm_39', 'tm_09'),
('Rm_40', 'tm_10'),
('Rm_41', 'tm_11'),
('Rm_42', 'tm_12'),
('Rm_43', 'tm_13'),
('Rm_44', 'tm_14'),
('Rm_45', 'tm_15'),
('Rm_46', 'tm_16'),
('Rm_47', 'tm_17'),
('Rm_48', 'tm_18'),
('Rm_49', 'tm_19'),
('Rm_50', 'tm_20');
-- Physician table
DROP TABLE IF EXISTS physician;
CREATE TABLE physician (
 physician_id VARCHAR(10) PRIMARY KEY,
 physician_name NVARCHAR(255) Not Null,
 physician_age INT Not Null ,
 physician_gender VARCHAR(10) Not Null,
 physician_cnic VARCHAR(15) Unique,
 physician_address NVARCHAR(500) Not Null,
 physician_phonenumber VARCHAR(20) Not Null,
 physician_qualification NVARCHAR(255) Not Null,
 physician_salary DECIMAL(10, 2) Not Null,
 patient_id VARCHAR(50) Not Null,
FOREIGN KEY (patient_id) REFERENCES patient(patient_id)
);
-- Inserting data into the new table structure
INSERT INTO physician (physician_id, physician_name, physician_age, physician_gender, physician_cnic, 
physician_address, physician_phonenumber, physician_qualification, physician_salary, patient_id) 
VALUES
('phy2_01', 'Dr. Sarah Ahmed', 40, 'Female', '32345-6789012-3', '22-B Gulberg III, Lahore, Pakistan', 
'0312-3456789', 'MBBS, FCPS', 120000.00, 'pat3_01'),
('phy3_02', 'Dr. Kamran Ali', 35, 'Male', '63456-7890123-4', 'House No. 5, Street 10, F-7/2, Islamabad, 
Pakistan', '0321-4567890', 'MBBS, MD', 110000.00, 'pat2_02'),
('phy2_03', 'Dr. Farah Khan', 42, 'Female', '44567-8901234-5', '15 Green Town, Phase 2, Karachi, 
Pakistan', '0333-5678901', 'MBBS, MS', 130000.00, 'pat3_03'),
('phy3_04', 'Dr. Naveed Malik', 38, 'Male', '35678-9012345-6', '7-C Model Town Extension, Multan, 
Pakistan', '0344-6789012', 'MBBS, FCPS', 115000.00, 'pat2_04'),
('phy2_05', 'Dr. Sana Riaz', 45, 'Female', '36789-0123456-7', 'Apartment #302, Liberty Market Tower, 
Faisalabad, Pakistan', '0315-7890123', 'MBBS, MD', 125000.00, 'pat3_05'),
('phy3_06', 'Dr. Imran Khan', 36, 'Male', '67890-1234567-8', '33 Canal Road, G-10/4, Islamabad, 
Pakistan', '0324-8901234', 'MBBS, MS', 118000.00, 'pat2_06'),
('phy2_07', 'Dr. Hina Malik', 39, 'Female', '38901-2345678-9', '18 Mall Road, Lahore Cantt, Lahore, 
Pakistan', '0336-9012345', 'MBBS, FCPS', 122000.00, 'pat3_07'),
('phy2_08', 'Dr. Ayesha Ahmed', 44, 'Female', '49012-3456789-0', 'House No. 12, Block 5, Clifton, 
Karachi, Pakistan', '0347-0123456', 'MBBS, MD', 128000.00, 'pat2_08'),
('phy3_09', 'Dr. Usman Ali', 37, 'Male', '40123-4567890-1', '25 Gulshan-e-Iqbal, Block 10-A, Karachi, 
Pakistan', '0318-1234567', 'MBBS, MS', 116000.00, 'pat3_09'),
('phy2_10', 'Dr. Sara Riaz', 41, 'Female', '31234-5678901-2', '9-A Satellite Town, Rawalpindi, Pakistan', 
'0327-2345678', 'MBBS, FCPS', 123000.00, 'pat3_10');
-- Department table
DROP TABLE IF EXISTS departmeent;
CREATE TABLE departmeent (
 departmeent_id varchar(50) PRIMARY KEY,
 departmeent_name NVARCHAR(500) Not Null,
 number_of_doctors INT Not Null
);
-- Insert data into the department table
INSERT INTO departmeent (departmeent_id, departmeent_name, number_of_doctors) VALUES
('dep_01', 'Cardiology', 4),
('dep_02', 'Orthopedics', 2),
('dep_03', 'Gynecology', 3),
('dep_04', 'Dermatology', 2),
('dep_05', 'General Surgery', 3),
('dep_06', 'Dentist', 2),
('dep_07', 'Ophthalmology', 4);
-- Doctor table
DROP TABLE IF EXISTS doctor;
-- Create the doctor table with corrected data types and foreign key reference
CREATE TABLE doctor (
 doctor_id VARCHAR(50) PRIMARY KEY,
 doctor_name NVARCHAR(200) NOT NULL,
 doctor_age INT NOT NULL,
 doctor_gender VARCHAR(25) NOT NULL,
 doctor_cnic VARCHAR(50) UNIQUE,
 doctor_phone VARCHAR(20) NOT NULL,
 doctor_address NVARCHAR(1000) NOT NULL,
 doctor_salary DECIMAL(10, 2) NOT NULL,
 doctor_qualification NVARCHAR(1000) NOT NULL,
 departmeent_id VARCHAR(50),
 FOREIGN KEY (departmeent_id) REFERENCES departmeent(departmeent_id)
);
-- Inserting data 
INSERT INTO doctor (doctor_id, doctor_name, doctor_age, doctor_gender, doctor_cnic, doctor_phone, 
doctor_address, doctor_salary, doctor_qualification, departmeent_id)
VALUES
('doc3_01', 'Dr. Ali Khan', 35, 'Male', '32345-6789012-3', '0312-1234567', '22B Gulberg III, Lahore, 
Pakistan', 100000.00, 'MBBS, FCPS', 'dep_01'),
('doc2_02', 'Dr. Aisha Malik', 40, 'Female', '63456-7890123-4', '0321-2345678', 'House No. 5, Street 10, 
F-7/2, Islamabad, Pakistan', 110000.00, 'MBBS, MD', 'dep_02'),
('doc3_03', 'Dr. Imran Ali', 45, 'Male', '44567-8901234-5', '0333-3456789', '27 Gulshan-e-Iqbal, Karachi, 
Pakistan', 120000.00, 'MBBS, MS', 'dep_03'),
('doc2_04', 'Dr. Saima Farooq', 38, 'Female', '35678-9012345-6', '0344-4567890', '7C Model Town 
Extension, Multan, Pakistan', 95000.00, 'MBBS, FCPS', 'dep_04'),
('doc3_05', 'Dr. Tariq Mahmood', 42, 'Male', '16789-0123456-7', '0315-5678901', 'Quetta Medical 
Center, Quetta, Pakistan', 110000.00, 'MBBS, MD', 'dep_05'),
('doc2_06', 'Dr. Sadia Riaz', 37, 'Female', '37890-1234567-8', '0324-6789012', 'Sialkot Medical Clinic, 
Sialkot, Pakistan', 98000.00, 'MBBS, MS', 'dep_06'),
('doc3_07', 'Dr. Bilal Khan', 36, 'Male', '38901-2345678-9', '0377-7890123', 'Rawalpindi Health Clinic, 
Rawalpindi, Pakistan', 115000.00, 'MBBS, FCPS', 'dep_07'),
('doc2_08', 'Dr. Hina Malik', 39, 'Female', '69012-3456789-0', '0388-8901234', 'House No. 8, Street 15, G9/1, Islamabad, Pakistan', 135000.00, 'MBBS, MRCP', 'dep_02'),
('doc3_09', 'Dr. Farhan Ahmed', 34, 'Male', '30123-4567890-1', '0399-9012345', '22B Gulberg III, Lahore, 
Pakistan', 102000.00, 'MBBS, MD', 'dep_03'),
('doc2_10', 'Dr. Samina Khan', 43, 'Female', '61234-5678901-2', '0320-1234567', 'House No. 8, Street 15, 
G-9/1, Islamabad, Pakistan', 128000.00, 'MBBS, FRCS', 'dep_01'),
('doc3_11', 'Dr. Usman Ali', 33, 'Male', '38765-4321098-7', '0331-2345678', 'Faisalabad Healthcare, 
Faisalabad, Pakistan', 107000.00, 'MBBS, MS', 'dep_02'),
('doc2_12', 'Dr. Sana Aziz', 44, 'Female', '37654-3210987-6', '0322-3456789', 'Peshawar Medical 
Institute, Peshawar, Pakistan', 132000.00, 'MBBS, FCPS', 'dep_03'),
('doc3_13', 'Dr. Imran Malik', 32, 'Male', '16543-2109876-5', '0333-4567890', 'Quetta General Hospital, 
Quetta, Pakistan', 104000.00, 'MBBS, MRCP', 'dep_01'),
('doc2_14', 'Dr. Zainab Ahmed', 36, 'Female', '35432-1098765-4', '0344-5678901', '14D Model Town, 
Lahore, Pakistan', 112000.00, 'MBBS, FCPS', 'dep_02'),
('doc3_15', 'Dr. Naveed Khan', 39, 'Male', '34321-0987654-3', '0325-6789012', 'Rawalpindi Medical 
Center, Rawalpindi, Pakistan', 130000.00, 'MBBS, MD', 'dep_03'),
('doc2_16', 'Dr. Ayesha Malik', 41, 'Female', '63210-9876543-2', '0306-7890123', 'House No. 5, Street 10, 
F-7/2, Islamabad, Pakistan', 118000.00, 'MBBS, FRCS', 'dep_01'),
('doc3_17', 'Dr. Fahad Ali', 35, 'Male', '32109-8765432-1', '0307-8901234', 'Faisalabad Medical Institute, 
Faisalabad, Pakistan', 123000.00, 'MBBS, MS', 'dep_02'),
('doc2_18', 'Dr. Saima Khan', 37, 'Female', '41098-7654321-0', '03088-9012345', '27 Gulshan-e-Iqbal, 
Karachi, Pakistan', 115000.00, 'MBBS, FCPS', 'dep_03'),
('doc3_19', 'Dr. Adnan Ahmed', 40, 'Male', '60987-6543210-9', '0329-0123456', 'House No. 5, Street 10, 
F-7/2, Islamabad, Pakistan', 128000.00, 'MBBS, MRCP', 'dep_01'),
('doc2_20', 'Dr. Rabia Aziz', 33, 'Female', '39876-5432109-8', '0344-1234567', 'Peshawar Healthcare, 
Peshawar, Pakistan', 105000.00, 'MBBS, MD', 'dep_02');
-- Invoice table
DROP TABLE IF EXISTS invoice;
CREATE TABLE invoice (
 invoice_id VARCHAR(50) PRIMARY KEY,
 invoice_date DATE Not Null,
 invoice_time TIME Not Null,
 invoice_fee DECIMAL(10, 2) Not Null,
 patient_id VARCHAR(50) REFERENCES patient(patient_id)
)
-- Insert data for invoices 
INSERT INTO invoice (invoice_id, invoice_date, invoice_time, invoice_fee, patient_id)
VALUES
('inv_01', '2024-01-01', '08:30:00', 150.00, 'pat3_01'),
('inv_02', '2024-01-01', '09:15:00', 200.00, 'pat2_02'),
('inv_03', '2024-01-01', '10:00:00', 175.00, 'pat3_03'),
('inv_04', '2024-01-01', '11:30:00', 180.00, 'pat2_04'),
('inv_05', '2024-01-02', '12:15:00', 220.00, 'pat3_05'),
('inv_06', '2024-01-02', '13:00:00', 190.00, 'pat2_06'),
('inv_07', '2024-01-02', '14:30:00', 210.00, 'pat3_07'),
('inv_08', '2024-01-02', '15:15:00', 185.00, 'pat2_08'),
('inv_09', '2024-01-02', '16:00:00', 200.00, 'pat3_09'),
('inv_10', '2024-01-2', '17:30:00', 175.00, 'pat3_10'),
('inv_11', '2024-01-3', '18:15:00', 160.00, 'pat3_11'),
('inv_12', '2024-01-3', '19:00:00', 195.00, 'pat2_12'),
('inv_13', '2024-01-3', '20:30:00', 180.00, 'pat3_13'),
('inv_14', '2024-01-3', '21:15:00', 225.00, 'pat2_14'),
('inv_15', '2024-01-3', '22:00:00', 190.00, 'pat3_15'),
('inv_16', '2024-01-3', '08:30:00', 210.00, 'pat2_16'),
('inv_17', '2024-01-3', '09:15:00', 185.00, 'pat3_17'),
('inv_18', '2024-01-4', '10:00:00', 200.00, 'pat2_18'),
('inv_19', '2024-01-4', '11:30:00', 175.00, 'pat3_19'),
('inv_20', '2024-01-4', '12:15:00', 160.00, 'pat2_20'),
('inv_21', '2024-01-5', '13:00:00', 195.00, 'pat2_21'),
('inv_22', '2024-01-5', '14:30:00', 180.00, 'pat3_22'),
('inv_23', '2024-01-5', '15:15:00', 225.00, 'pat2_23'),
('inv_24', '2024-01-5', '16:00:00', 190.00, 'pat3_24'),
('inv_25', '2024-01-5', '17:30:00', 210.00, 'pat2_25'),
('inv_26', '2024-01-6', '18:15:00', 185.00, 'pat3_26'),
('inv_27', '2024-01-6', '19:00:00', 200.00, 'pat2_27'),
('inv_28', '2024-01-7', '20:30:00', 175.00, 'pat3_28'),
('inv_29', '2024-01-7', '21:15:00', 160.00, 'pat2_29'),
('inv_30', '2024-01-7', '22:00:00', 195.00, 'pat3_30');
-- Appointment table
DROP TABLE IF EXISTS appointment;
CREATE TABLE appointment (
 appointment_id VARCHAR(50) PRIMARY KEY,
 appointment_date DATE Not Null,
 appointment_time TIME Not Null,
 patient_id VARCHAR(50) REFERENCES patient(patient_id)
);
-- Insert data appointment 
INSERT INTO appointment (appointment_id, appointment_date, appointment_time, patient_id)
VALUES
('app_01', '2024-01-01', '08:30:00', 'pat3_01'),
('app_08', '2024-01-01', '15:15:00', 'pat3_13'),
('app_15', '2024-01-01', '22:00:00', 'pat3_28'),
('app_02', '2024-01-02', '09:15:00', 'pat2_12'),
('app_09', '2024-01-02', '16:00:00', 'pat3_09'),
('app_16', '2024-01-02', '08:30:00', 'pat2_16'),
('app_03', '2024-01-03', '10:00:00', 'pat3_03'),
('app_10', '2024-01-03', '17:30:00', 'pat3_10'),
('app_04', '2024-01-04', '11:30:00', 'pat3_07'),
('app_11', '2024-01-04', '18:15:00', 'pat3_11'),
('app_18', '2024-01-04', '10:00:00', 'pat2_18'),
('app_05', '2024-01-05', '12:15:00', 'pat3_05'),
('app_12', '2024-01-05', '19:00:00', 'pat3_22'),
('app_19', '2024-01-05', '11:30:00', 'pat3_19'),
('app_13', '2024-01-06', '20:30:00', 'pat2_02'),
('app_07', '2024-01-07', '14:30:00', 'pat2_21'),
('app_14', '2024-01-07', '21:15:00', 'pat2_14');
-- Emergency table 
DROP TABLE IF EXISTS emergency;
CREATE TABLE emergency (
 recovered_cases INT Not Null,
 in_recovery INT Not Null,
 death_toll INT Not Null,
 room_no VARCHAR(10) PRIMARY KEY,
 doctor_id VARCHAR(50) REFERENCES doctor(doctor_id),
 patient_id VARCHAR(50) REFERENCES patient(patient_id)
);
-- Inserting data 
INSERT INTO emergency (patient_id, doctor_id, room_no, recovered_cases, in_recovery, death_toll)
VALUES
('pat3_01', 'doc3_01', 'Rm_01', 5, 1, 2),
('pat2_02', 'doc3_03', 'Rm_02', 8, 0, 3),
('pat2_04', 'doc3_05', 'Rm_03', 12, 1, 1),
('pat2_06', 'doc2_08', 'Rm_04', 3, 0, 5),
('pat3_09', 'doc2_10', 'Rm_05', 10, 1, 2),
('pat3_11', 'doc2_12', 'Rm_06', 6, 0, 4);
-- Prescription table
DROP TABLE IF EXISTS prescription;
CREATE TABLE prescription (
 patient_id VARCHAR(50) REFERENCES patient(patient_id),
 doctor_id VARCHAR(50) REFERENCES doctor(doctor_id),
 prescription_id VARCHAR(10) PRIMARY KEY,
 disease_name VARCHAR(50) Not Null,
 medicines VARCHAR(100) Not Null,
 recommendation NVARCHAR(250) Not Null
);
-- Insert data for prescriptions
INSERT INTO prescription (patient_id, doctor_id, prescription_id, disease_name, medicines, 
recommendation) 
VALUES
('pat3_01', 'doc3_01', 'presc_01', 'Fever', 'Paracetamol', 'Rest and stay hydrated.'),
('pat2_02', 'doc3_03', 'presc_02', 'Headache', 'Aspirin', 'Get plenty of rest and stay in a quiet 
environment.'),
('pat3_03', 'doc3_05', 'presc_03', 'Stomachache', 'Antacids', 'Avoid spicy foods and drink plenty of 
water.'),
('pat2_04', 'doc3_07', 'presc_04', 'Sprained Ankle', 'Pain relievers', 'Rest and elevate the affected leg.'),
('pat3_05', 'doc3_09', 'presc_05', 'Common Cold', 'Cough syrup', 'Stay warm and get enough sleep.'),
('pat2_06', 'doc3_11', 'presc_06', 'Allergies', 'Antihistamines', 'Avoid allergens and keep your 
environment clean.'),
('pat3_07', 'doc3_13', 'presc_07', 'Stomach Flu', 'Hydration solution', 'Rest and avoid solid foods.'),
('pat2_08', 'doc3_15', 'presc_08', 'Migraine', 'Pain relievers', 'Find a quiet, dark room and rest during an 
attack.'),
('pat3_09', 'doc3_17', 'presc_09', 'Nervousness', 'Relaxation exercises', 'Practice deep breathing and 
relaxation techniques.'),
('pat3_10', 'doc3_19', 'presc_10', 'Indigestion', 'Antacids', 'Eat smaller meals and avoid lying down after 
eating.'),
('pat3_11', 'doc2_02', 'presc_11', 'Sleep Issues', 'Melatonin', 'Establish a regular sleep schedule and 
create a calming bedtime routine.'),
('pat2_12', 'doc2_04', 'presc_12', 'High Blood Pressure', 'Lifestyle changes', 'Adopt a low-sodium diet and 
exercise regularly.'),
('pat3_13', 'doc2_06', 'presc_13', 'Hay Fever', 'Nasal spray', 'Avoid allergens and keep windows closed 
during high pollen seasons.'),
('pat2_14', 'doc2_08', 'presc_14', 'Urinary Tract Infection', 'Antibiotics', 'Stay hydrated and complete the 
full course of antibiotics.'),
('pat3_15', 'doc2_10', 'presc_15', 'Feeling Down', 'Encouragement', 'Talk about your feelings and seek 
support from loved ones.'),
('pat2_16', 'doc2_12', 'presc_16', 'Acne', 'Topical treatment', 'Keep your face clean and avoid squeezing 
pimples.'),
('pat3_17', 'doc2_14', 'presc_17', 'Joint Pain', 'Pain relievers', 'Engage in gentle exercises and maintain a 
healthy weight.'),
('pat2_18', 'doc2_16', 'presc_18', 'Upset Stomach', 'Antacids', 'Avoid spicy foods and drink peppermint 
tea.'),
('pat3_19', 'doc2_18', 'presc_19', 'Breathing Issues', 'Bronchodilators', 'Avoid triggers and practice deep 
breathing exercises.'),
('pat2_20', 'doc2_20', 'presc_20', 'Sinus Trouble', 'Decongestants', 'Stay hydrated and use a humidifier to 
relieve nasal congestion.'),
('pat2_21', 'doc3_01', 'presc_21', 'Back Pain', 'Pain relievers', 'Apply heat or ice and avoid prolonged 
sitting or standing.'),
('pat3_22', 'doc3_03', 'presc_22', 'Diabetes Support', 'Lifestyle changes', 'Monitor blood sugar levels 
regularly and follow a balanced diet.'),
('pat2_23', 'doc3_05', 'presc_23', 'Thyroid Management', 'Medication adjustment', 'Follow up with 
regular thyroid function tests and medication adjustments.'),
('pat3_24', 'doc3_07', 'presc_24', 'Eye Redness', 'Eye drops', 'Avoid touching your eyes and practice good 
hand hygiene.'),
('pat2_25', 'doc3_09', 'presc_25', 'Low Iron Levels', 'Iron supplements', 'Include iron-rich foods in your 
diet.'),
('pat3_26', 'doc3_11', 'presc_26', 'Gout', 'Pain relievers', 'Limit intake of certain foods and stay 
hydrated.'),
('pat2_27', 'doc3_13', 'presc_27', 'Breathing Difficulty', 'Inhalers', 'Quit smoking and follow your 
treatment plan.'),
('pat3_28', 'doc3_15', 'presc_28', 'Digestive Issues', 'Antacids', 'Avoid spicy foods and eat smaller, more 
frequent meals.'),
('pat2_29', 'doc3_17', 'presc_29', 'Skin Irritation', 'Topical treatment', 'Keep the affected area clean and 
moisturized.'),
('pat3_30', 'doc3_19', 'presc_30', 'Gluten Sensitivity', 'Gluten-free diet', 'Avoid foods containing gluten 
and read labels carefully.');
-- Pharmacy table
DROP TABLE IF EXISTS pharmacy;
CREATE TABLE pharmacy (
 medicine_names VARCHAR(100) Not Null,
 purchase_id VARCHAR(10) PRIMARY KEY,
 pharmacy_fee DECIMAL(10, 2) Not Null
);
-- Insert data for pharmacy records
INSERT INTO pharmacy (medicine_names, purchase_id, pharmacy_fee)
VALUES
('Paracetamol', 'pur_01', 15.00),
('Aspirin', 'pur_02', 12.50),
('Amlodipine', 'pur_03', 25.00),
('Cough Syrup', 'pur_04', 18.75),
('Antacids', 'pur_05', 10.50),
('Pain Relievers', 'pur_06', 20.00),
('Eye Drops', 'pur_07', 22.50),
('Antibiotics', 'pur_08', 30.00),
('Melatonin', 'pur_09', 17.25),
('Hydration Solution', 'pur_10', 14.75),
('Nasal Spray', 'pur_11', 21.25),
('Bronchodilators', 'pur_12', 28.50),
('Topical Treatment', 'pur_13', 16.25),
('Iron Supplements', 'pur_14', 12.00),
('Relaxation Exercises', 'pur_15', 19.75),
('Lifestyle Changes', 'pur_16', 24.50),
('Decongestants', 'pur_17', 15.75),
('Gluten-Free Diet', 'pur_18', 18.25),
('Pain Relievers', 'pur_19', 22.00),
('Encouragement', 'pur_20', 14.50),
('Medication Adjustment', 'pur_21', 26.75),
('Eye Drops', 'pur_22', 20.25),
('Antacids', 'pur_23', 12.75),
('Antihistamines', 'pur_24', 16.50),
('Pain Relievers', 'pur_25', 19.00),
('Hydration Solution', 'pur_26', 23.25),
('Cough Syrup', 'pur_27', 14.50),
('Antibiotics', 'pur_28', 27.75),
('Topical Treatment', 'pur_29', 18.25),
('Iron Supplements', 'pur_30', 13.50),
('Relaxation Exercises', 'pur_31', 21.75),
('Lifestyle Changes', 'pur_32', 26.50),
('Decongestants', 'pur_33', 17.75),
('Gluten-Free Diet', 'pur_34', 20.25),
('Pain Relievers', 'pur_35', 23.00),
('Encouragement', 'pur_36', 15.50),
('Medication Adjustment', 'pur_37', 28.75),
('Eye Drops', 'pur_38', 22.25),
('Antacids', 'pur_39', 14.75),
('Antihistamines', 'pur_40', 18.50);
-- Interny table
DROP TABLE IF EXISTS interny;
CREATE TABLE interny (
 interny_id VARCHAR(10) PRIMARY KEY,
 interny_name NVARCHAR(255) Not Null,
 interny_gender VARCHAR(10) Not Null,
 interny_cnic VARCHAR(15) Unique,
 admission_date DATE Not Null,
 supervisor VARCHAR(50) REFERENCES doctor(doctor_id),
 interny_address NVARCHAR(1000) Not Null
);
-- Inserting data 
INSERT INTO interny (interny_id, interny_name, interny_gender, interny_cnic, admission_date, 
supervisor, interny_address) VALUES
('int3_01', 'Ali Khan', 'Male', '32345-6789012-3', '2023-05-15', 'doc3_01', '22B Gulberg III, Lahore, 
Pakistan'),
('int2_02', 'Fatima Ahmed', 'Female', '63456-7890123-4', '2023-06-10', 'doc2_02', 'House No. 5, Street 
10, F-7/2, Islamabad, Pakistan'),
('int3_03', 'Imran Malik', 'Male', '44567-8901234-5', '2023-07-05', 'doc3_03', '15 Green Town, Phase 2, 
Karachi, Pakistan'),
('int2_04', 'Saba Farooq', 'Female', '35678-9012345-6', '2023-08-20', 'doc2_04', '7C Model Town 
Extension, Multan, Pakistan'),
('int3_05', 'Tahir Wilson', 'Male', '36789-0123456-7', '2023-09-15', 'doc3_05', 'Apartment #302, Liberty 
Market Tower, Faisalabad, Pakistan'),
('int2_06', 'Ayesha Riaz', 'Female', '67890-1234567-8', '2023-10-10', 'doc2_06', '33 Canal Road, G-10/4, 
Islamabad, Pakistan'),
('int3_07', 'Zain Harris', 'Male', '38901-2345678-9', '2023-11-05', 'doc3_07', '18 Mall Road, Lahore Cantt, 
Lahore, Pakistan'),
('int2_08', 'Noor Brown', 'Female', '49012-3456789-0', '2023-12-20', 'doc2_08', 'House No. 12, Block 5, 
Clifton, Karachi, Pakistan'),
('int3_09', 'Usman Taylor', 'Male', '40123-4567890-1', '2024-01-15', 'doc3_09', '25 Gulshan-e-Iqbal, Block 
10-A, Karachi, Pakistan'),
('int2_10', 'Saima Batool', 'Female', '31234-5678901-2', '2024-02-10', 'doc2_10', '9A Satellite Town, 
Rawalpindi, Pakistan');
-- Radiographic_imaging table
DROP TABLE IF EXISTS radiographic_imaging;
CREATE TABLE radiographic_imaging (
 room_no VARCHAR(10) REFERENCES rooms(room_no),
 tool_machinery_id VARCHAR(10) REFERENCES tool_machinery(tool_machinery_id),
 staff_id VARCHAR(10) REFERENCES staff(staff_id),
 doctor_id VARCHAR(50) REFERENCES doctor(doctor_id)
);
-- Insert data 
INSERT INTO radiographic_imaging (room_no, tool_machinery_id, staff_id, doctor_id) 
VALUES
('Rm_01', 'tm_01', 'stf3_01', 'doc3_01'),
('Rm_02', 'tm_02', 'stf2_02', 'doc2_02'),
('Rm_03', 'tm_03', 'stf3_03', 'doc3_03'),
('Rm_04', 'tm_04', 'stf2_04', 'doc2_04'),
('Rm_05', 'tm_05', 'stf3_05', 'doc3_05');
-- Laboratory table
DROP TABLE IF EXISTS laboratory;
CREATE TABLE laboratory (
 lab_report_no VARCHAR(10) PRIMARY KEY,
 doctor_id VARCHAR(50) REFERENCES doctor(doctor_id),
 tool_machinery_id VARCHAR(10) REFERENCES tool_machinery(tool_machinery_id),
 patient_id VARCHAR(50) REFERENCES patient(patient_id)
);
-- Insert data for 
INSERT INTO laboratory (lab_report_no, doctor_id, tool_machinery_id, patient_id) 
VALUES
('LR_001', 'doc3_01', 'tm_01', 'pat3_01'),
('LR_002', 'doc2_02', 'tm_02', 'pat2_02'),
('LR_003', 'doc3_03', 'tm_03', 'pat3_03'),
('LR_004', 'doc2_04', 'tm_04', 'pat2_04'),
('LR_005', 'doc3_05', 'tm_05', 'pat3_05'),
('LR_006', 'doc2_06', 'tm_06', 'pat2_06'),
('LR_007', 'doc3_07', 'tm_07', 'pat3_07'),
('LR_008', 'doc2_08', 'tm_08', 'pat2_08'),
('LR_009', 'doc3_09', 'tm_09', 'pat3_09'),
('LR_010', 'doc2_10', 'tm_10', 'pat3_10'),
('LR_011', 'doc3_11', 'tm_11', 'pat3_11') ;
--Insurance table
DROP TABLE IF EXISTS insurance;
CREATE TABLE insurance (
 insurance_id VARCHAR(15) PRIMARY KEY,
 insurance_company VARCHAR(255) Not Null,
 insurance_start_date DATE Not Null,
 insurance_end_date DATE Not Null,
 patient_id varchar(50) Not Null,
 FOREIGN KEY (patient_id) REFERENCES patient(patient_id)
);
-- Insert data 
INSERT INTO insurance (insurance_id, insurance_company, insurance_start_date, insurance_end_date, 
patient_id)
VALUES
 ('Ins_01', 'Jubilee General Insurance Company Limited', '2024-01-15', '2025-01-15', 'pat3_01'),
 ('Ins_02', 'Adamjee Insurance Company Limited', '2024-02-15', '2025-02-15', 'pat2_02'),
 ('Ins_03', 'EFU General Insurance Ltd.', '2024-03-15', '2025-03-15', 'pat3_03'),
 ('Ins_04', 'Askari General Insurance Company Limited', '2024-04-15', '2025-04-15', 'pat2_04'),
 ('Ins_05', 'TPL Insurance Limited', '2024-05-15', '2025-05-15', 'pat3_05'),
 ('Ins_06', 'IGI General Insurance Limited', '2024-06-15', '2025-06-15', 'pat2_06'),
 ('Ins_07', 'SPI Insurance Company Limited', '2025-08-01', '2026-08-01', 'pat2_20');
DROP TABLE IF EXISTS accountant
CREATE TABLE accountant (
 ID INT PRIMARY KEY,
 name VARCHAR(100), -- Increased length for potential longer names
 age INT,
 qualification VARCHAR(100), -- Increased length for potential longer qualifications
 cnic VARCHAR(15) UNIQUE, -- Added UNIQUE constraint
 address VARCHAR(200), -- Increased length for potential longer addresses
 phone_no VARCHAR(15), -- Ensure this field only contains phone numbers
 salary DECIMAL(10, 2)
);
-- Create the procedure
DROP PROC IF EXISTS InsertAccountant; 
CREATE PROCEDURE InsertAccountant
 @p_ID INT,
 @p_name VARCHAR(100), -- Increased length for potential longer names
 @p_age INT,
 @p_qualification VARCHAR(100), -- Increased length for potential longer qualifications
 @p_cnic VARCHAR(15),
 @p_address VARCHAR(200), -- Increased length for potential longer addresses
 @p_phone_no VARCHAR(15), -- Ensure this field only contains phone numbers
 @p_salary DECIMAL(10, 2)
AS
BEGIN
 -- Insert data
 INSERT INTO accountant (ID, name, age, qualification, cnic, address, phone_no, salary) 
 VALUES (@p_ID, @p_name, @p_age, @p_qualification, @p_cnic, @p_address, @p_phone_no, 
@p_salary);
select* from accountant;
END;
-- Insert sample data into the accountant table
EXEC InsertAccountant 1, 'John Doe', 30, 'Chartered Accountant', '12345-1234567-1', 'Lahore, Pakistan', 
'+923001234567', 50000.00;
EXEC InsertAccountant 2, 'Jane Smith', 35, 'CPA', '12345-2345678-1', 'Karachi, Pakistan', 
'+923012345678', 60000.00;
EXEC InsertAccountant 3, 'Alice Johnson', 28, 'MBA Finance', '12345-3456789-1', 'Islamabad, Pakistan', 
'+923023456789', 55000.00;
EXEC InsertAccountant 4, 'Bob Williams', 40, 'ACCA', '12345-4567890-1', 'Rawalpindi, Pakistan', 
'+923034567890', 65000.00;
EXEC InsertAccountant 5, 'Emily Davis', 32, 'CIMA', '12345-5678901-1', 'Faisalabad, Pakistan', 
'+923045678901', 60000.00;

```


