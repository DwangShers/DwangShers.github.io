---
Title: DBS101 Flipped Class 2
categories: [DBS101, Flipped_Class2]
tags: [DBS101]
---

### Topic : Entity Relationship Diagram
----

In our second flipped class, we were divided into groups of 4 students to work on an Entity Relationship Diagram. Each group was assigned one topic to create an Entity Relationship Diagram, and we were given 50 minutes for discussion and preparation. After the discussion, each group was given 10 minutes for a class presentation.

---
From this flipped class, it was expected for us to understand Entity Relationship Modeling and learn to draw Entity Relationship Diagram for a real world system.
For our flipped class, our tutor provided us resources for us to get more information.

Website link: "https://www.tutorialspoint.com/dbms/er_diagram_representation.htm"

From Textbook/eBook.(Database systems fundamentals, unit 6)

---
The topic that my group got was to create ERD for an "Online health book(E-health) system" which focuses on health records.
From flipped class I have summed up and drew a ERD diagram which represents "E-health".
![Alt text](/image/msg6414658906-20071.jpg)

#### Entities: 

1)Patient

2)Health

3)Prescription 

4)Diagnosis

5)Appointment

6)Healthcare Provider

#### Relationships:
* Patients have Health Records.
* Patients can have Appointments with Healthcare Providers.
* Health Records contain Diagnoses and Prescriptions.
* Healthcare Providers make Diagnoses and Prescribe Medications.
* Appointments are scheduled between Patients and Healthcare Providers.

#### Mapping Cardinalities:
* Patients ---(1:N)--- Health Record. [one patient can have one or more health record] 

* Health Record --(1:N)--- Prescription. [Health record can have one or more prescription]

* Health Record ---(1:1)--- Diagnosis. [one health record can have one diagnosis]

* Diagnosis ---(N:1)--- Healthcare Provider. [One healthcare provider can have one or many diagnosis]

In the given diagram, the "Diagnosis" entity which is inside the double rectangle is considered weak entity because it doesn't have its own primary key.

The reason for "Medication Name" being multivalued is that a single prescription cna involve the administration in multiple medications simultaneously.