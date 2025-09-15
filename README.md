# Sahohime OMOP CDM data

The project is based on converting the Sahohime dataset into the [OMOP Common Data Model (CDM) v5.4 format](https://ohdsi.github.io/CommonDataModel/cdm54.html). [Sahohime](https://www.ohdsi-japan.org/pseudodata) is a publicly available pseudonymized health dataset provided by [OHDSI Japan](https://www.ohdsi-japan.org/). It was designed as a synthetic dataset that mimics the structure and characteristics of real clinical data, allowing researchers to develop, test, and demonstrate data models and analytic pipelines without handling sensitive personal information. By using Sahohime as the source, this project ensures reproducibility, transparency, and data privacy while showcasing how Japanese healthcare data can be harmonized into OMOP CDM for international interoperability and collaborative research.

## person
This table serves as the central identity management for all Persons in the database. It contains records that uniquely identify each person or patient, and some demographic information.
- [person.csv](https://github.com/ogishimalab/sahohime_omop_cdm/blob/main/person.csv)

## obeservation_period
This table contains records which define spans of time during which two conditions are expected to hold: (i) Clinical Events that happened to the Person are recorded in the Event tables, and (ii) absence of records indicate such Events did not occur during this span of time.
- [observation_period.csv](https://github.com/ogishimalab/sahohime_omop_cdm/blob/main/observation_period.csv)

## visit_occurrence
This table contains Events where Persons engage with the healthcare system for a duration of time. They are often also called “Encounters”. Visits are defined by a configuration of circumstances under which they occur, such as (i) whether the patient comes to a healthcare institution, the other way around, or the interaction is remote, (ii) whether and what kind of trained medical staff is delivering the service during the Visit, and (iii) whether the Visit is transient or for a longer period involving a stay in bed.
- [visit_occurrence.csv](https://github.com/ogishimalab/sahohime_omop_cdm/blob/main/visit_occurrence.csv)

## condition_occurrence
This table contains records of Events of a Person suggesting the presence of a disease or medical condition stated as a diagnosis, a sign, or a symptom, which is either observed by a Provider or reported by the patient.
- [condition_occurrence.csv](https://github.com/ogishimalab/sahohime_omop_cdm/blob/main/condition_occurrence.csv)

## drug_exposure
This table captures records about the exposure to a Drug ingested or otherwise introduced into the body. A Drug is a biochemical substance formulated in such a way that when administered to a Person it will exert a certain biochemical effect on the metabolism. Drugs include prescription and over-the-counter medicines, vaccines, and large-molecule biologic therapies. Radiological devices ingested or applied locally do not count as Drugs.
- [drug_exposure.csv](https://github.com/ogishimalab/sahohime_omop_cdm/blob/main/drug_exposure.csv)

## procedure_occurrence
This table contains records of activities or processes ordered by, or carried out by, a healthcare provider on the patient with a diagnostic or therapeutic purpose.
- [procedure_occurrence.csv](https://github.com/ogishimalab/sahohime_omop_cdm/blob/main/procedure_occurrence.csv)

## measurement
The MEASUREMENT table contains records of Measurements, i.e. structured values (numerical or categorical) obtained through systematic and standardized examination or testing of a Person or Person’s sample. The MEASUREMENT table contains both orders and results of such Measurements as laboratory tests, vital signs, quantitative findings from pathology reports, etc. Measurements are stored as attribute value pairs, with the attribute as the Measurement Concept and the value representing the result. The value can be a Concept (stored in VALUE_AS_CONCEPT), or a numerical value (VALUE_AS_NUMBER) with a Unit (UNIT_CONCEPT_ID). The Procedure for obtaining the sample is housed in the PROCEDURE_OCCURRENCE table, though it is unnecessary to create a PROCEDURE_OCCURRENCE record for each measurement if one does not exist in the source data. Measurements differ from Observations in that they require a standardized test or some other activity to generate a quantitative or qualitative result. If there is no result, it is assumed that the lab test was conducted but the result was not captured.
- [measurement.csv](https://github.com/ogishimalab/sahohime_omop_cdm/blob/main/measurement.csv)

## License
This dataset is licensed under the Creative Commons Attribution-ShareAlike 4.0 International License (CC BY-SA 4.0).
It is derived from Sahohime (https://www.ohdsi-japan.org/pseudodata/) and Sahohime OMOP-CDM Data (https://github.com/ogishimalab/sahohime_omop_cdm/), and any redistribution or adaptation must acknowledge these original sources.

