---
title: Konfigurera integrering med Finance
description: I denna artikel beskrivs integreringen mellan Dynamics 365 Human Resources och Dynamics 365 Finance.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8be7cbf92c11036d334516116f0895c426380954
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8875870"
---
# <a name="configure-integration-with-finance"></a>Konfigurera integrering med Finance


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



För att integrera Dynamics 365 Human Resources med Dynamics 365 Finance kan du använda Personal till Ekonomi-mallen i [Dataintegrerare](/powerapps/administrator/data-integrator). Med mallen personal till ekonomi kan dataflöden för jobb, befattningar och medarbetare användas. Med hjälp av mallen kan dataflöda från personal till ekonomi, men tillåter inte att data flödar från ekonomi till personal.

![Integreringsflöde Personal till Ekonomi.](./media/hr-admin-integration-finance-flow.png)

Lösningen personal till ekonomi innehåller följande typer av datasynkronisering:

- Underhåll jobb i personal och synkronisera dem från personal till ekonomi.
- Underhåll positioner och positionstilldelningar i personal och synkronisera dem från personal till ekonomi
- Underhåll anställningar i personal och synkronisera dem från personal till ekonomi
- Underhåll medarbetare och arbetaradresser i personal och synkronisera dem från personal till ekonomi

## <a name="system-requirements-for-human-resources"></a>Systemkrav för personal

Integreringslösningen kräver följande versioner av personal och ekonomi: 

- Dynamics 365 Human Resources den Dataverse
- Dynamics 365 Finance version 7.2 och senare

## <a name="template-and-tasks"></a>Mall och uppgifter

Om du vill öppna mallen personal till ekonomi.

1. Öppna [Power Apps administrationscenter](https://admin.powerapps.com/). 

2. Välj **Projekt** och välj sedan **Nytt projekt** i det övre högra hörnet. Skapa ett nytt projekt för varje juridisk person som du vill integrera i ekonomi.

3. Välj **Personal (personal Dataverse till ekonomi)** för att synkronisera poster från personal till ekonomi.

Mallen använder följande underliggande uppgifter för att synkronisera poster från personal till ekonomi:

- **Jobbfunktioner för kompensationsjobbfunktion**
- **Avdelningar till driftenhet**
- **Jobbtyper för kompensationsjobbtyp**
- **Jobb till jobb**
- **Jobb till jobbdetalj**
- **Befattningstyper till befattningstyp**
- **Jobbefattningar till grundläggande befattning**
- **Jobbefattningar till befattningsdetaljer**
- **Jobbefattningar till befattningstidslängd**
- **Jobbefattningar till befattningshierarkier**
- **Arbetare till medarbetare**
- **Anställning till anställning**
- **Anställning till anställningsdetalj**
- **Befattningstilldelning för medarbetare till Befattningstilldelningar för medarbetare**
- **Adress till medarbetare till postadress V2 till medarbetare**

## <a name="template-mappings"></a>Mallmappningar

I följande mappningstabeller för mallar innehåller namnet på uppgiften de entiteter som används i varje program. Källan (personal) ligger till vänster och destinationen (ekonomi) är till höger.

### <a name="job-functions-to-compensation-job-function"></a>Jobbfunktioner för kompensationsjobbfunktion

| Dataverse-register (källa) | Entiteten ekonomi (destination) |
|-------------------------------------|---------------------------------------------|
| cdm_name (cdm_Job   Funktionsnamn)  | JOBFUNCTIONID   (JOBFUNCTIONID)            |
| cdm_description   (cdm_description) | BESKRIVNING   (BESKRIVNING)                 |

### <a name="departments-to-operating-unit"></a>Avdelningar till driftenhet

| Dataverse-register (källa)           | Entiteten ekonomi (destination) |
|-----------------------------------------------|---------------------------------------------|
| cdm_name (cdm_name)                           | NAME (NAME)                                 |
| cdm_departmentnumber   (cdm_departmentnumber) | OPERATINGUNITNUMBER   (OPERATINGUNITNUMBER) |
|                                               | OPERATINGUNITTYPE   (OPERATINGUNITTYPE)     |
| cdm_description   (cdm_description)           | NAMEALIAS   (NAMEALIAS)                     |

### <a name="job-types-to-compensation-job-type"></a>Jobbtyper för kompensationsjobbtyp

| Dataverse-register (källa)   | Entiteten ekonomi (destination) |
|---------------------------------------|---------------------------------------------|
| cdm_name (cdm_name)                   | JOBTYPEID   (JOBTYPEID)                     |
| cdm_description   (cdm_description)   | BESKRIVNING   (BESKRIVNING)                 |
| cdm_exemptstatus   (cdm_exemptstatus) | EXEMPTSTATUS   (EXEMPTSTATUS)               |

### <a name="jobs-to-jobs"></a>Jobb till jobb

| Dataverse-register (källa)                           | Entiteten ekonomi (destination)           |
|---------------------------------------------------------------|-------------------------------------------------------|
| cdm_name (cdm_name)                                           | JOBID (JOBID)                                         |
| cdm_maximumnumberofpositions   (cdm_maximumnumberofpositions) | MAXIMUMNUMBEROFPOSITIONS   (MAXIMUMNUMBEROFPOSITIONS) |
| cdm_allowedunlimitedpositions   (cdm_allowunlimitedpositions) | ALLOWUNLIMITEDPOSITIONS   (ALLOWUNLIMITEDPOSITIONS)   |
| cdm_description   (cdm_description)                           | BESKRIVNING   (BESKRIVNING)                           |
| cdm_jobdescription   (cdm_jobdescription)                     | JOBDESCRIPTION   (JOBDESCRIPTIONS)                    |

### <a name="jobs-to-job-detail"></a>Jobb till jobbdetalj

| Dataverse-register (källa)                             | Entiteten ekonomi (destination) |
|-----------------------------------------------------------------|---------------------------------------------|
| cdm_name (cdm_name)                                             | JOBID (JOBID)                               |
| cdm_jobtypeid.cdm_name   (Jobbtyp (jobbtypnamn))             | JOBTYPEID   (JOBTYPEID)                     |
| cdm_jobfunctionid.cdm_name   (Jobbfunktion (jobbfunktionsnamn)) | FUNCTIONID   (FUCNTIONID)                   |
| cdm_validfrom   (giltigt från)                                    | VALIDFROM   (VALIDFROM)                     |
| cdm_validto (giltigt till)                                        | VALIDTO (VALIDTO)                           |
| cdm_defaultfulltimeequivalent   (Heltidslön)   | FULLTIMEEQUIVALENT   (FULLTIMEEQUIVALENT)   |

### <a name="position-types-to-position-type"></a>Befattningstyper till befattningstyp

| Dataverse-register (källa)       | Entiteten ekonomi (destination) |
|-------------------------------------------|---------------------------------------------|
| cdm_name (cdm_name)                       | POSITIONTYPEID   (POSITIONTYPEID)           |
| cdm_description   (cdm_description)       | BESKRIVNING   (BESKRIVNING)                 |
| cdm_classification   (cdm_classification) | KLASSIFICERING   (KLASSIFICERING)           |

### <a name="job-positions-to-base-position"></a>Jobbefattningar till grundläggande befattning

| Dataverse-register (källa)           | Entiteten ekonomi (destination) |
|-----------------------------------------------|---------------------------------------------|
| cdm_jobpositionnumber   (Jobbefattningsnummer) | POSITIONID (POSITIONID)                      |

### <a name="job-positions-to-position-details"></a>Jobbefattningar till befattningsdetaljer

| Dataverse-register (källa)              | Entiteten ekonomi (destination)       |
|--------------------------------------------------------------------------|---------------------------------------------------|
| cdm_jobpositionnumber  (Jobbefattningsnummer)                            | POSITIONID (POSITIONID)                             |
| cdm_jobid.cdm_name   (Jobb (Namn))                                        | JOBID (JOBID)                                    |
| cdm_description   (cdm_description)                                        | BESKRIVNING   (BESKRIVNING)                       |
| cdm_departmentid.cdm_departmentnumber   (avdelning (avdelningsnummer)) | DEPARTMENTNUMBER   (DEPARTMENTNUMBER)             |
| cdm_positiontypeid.cdm_name   (Befattningstyp (Namn))                     | POSITIONTYPEID   (POSITIONTYPEID)                 |
| cdm_avaialableforassignment   (tillgänglig för tilldelning)                 | AVAILABLEFORASSIGNMENT   (AVAILABLEFORASSIGNMENT) |
| cdm_validfrom   (giltigt från)                                            | VALIDFROM   (VALIDFROM)                           |
| cdm_validto (giltigt till)                                                 | VALIDTO (VALIDTO)                               |
| cdm_fulltimeequivalent   (Heltidslön)                           | FULLTIMEEQUIVALENT   (FULLTIMEEQUIVALENT)         |

### <a name="job-positions-to-position-durations"></a>Jobbefattningar till befattningstidslängd

| Dataverse-register (källa)             | Entiteten ekonomi (destination) |
|-------------------------------------------------|---------------------------------------------|
| cdm_jobpositionnumber   (Jobbefattningsnummer)   | POSITIONID (POSITIONID)                      |
| Beräknad     aktivering (beräknad aktivering) | VALIDFROM (VALIDFROM)                        |
| Beräknad     Pension (beräknad pension) | VALIDTO (VALIDTO)                         |

### <a name="job-positions-to-position-hierarchies"></a>Jobbefattningar till befattningshierarkier

| Dataverse-register (källa)        | Entiteten ekonomi (destination) |
|-----------------------------------------------------------------------------------------------|---------------------------------------------|
| cdm_jobpositionnumber   (Jobbefattningsnummer)                                                 | POSITIONID(POSITIONID)                      |
| cdm_parentjobpositionid.cdmjobpositionnumber   (cdm_parentjobpositionid.cdmjobpositionnumber) | PARENTPOSITIONID (PARENTPOSITIONID)         |
| cdm_validfrom   (giltigt från)                                                                  | VALIDFROM   (VALIDFROM)                     |
| cdm_validto (giltigt   till)                                                                      | VALIDTO (VALIDTO)                           |
| HIERARCHYTYPENAME   (HIERARCHYTYPENAME)                                                       | HIERARCHYTYPENAME   (HIERARCHYTYPENAME)     |


### <a name="workers-to-worker"></a>Arbetare till medarbetare
| Dataverse-register (källa)           | Entiteten ekonomi (destination)       |
|-----------------------------------------------|---------------------------------------------------|
| cdm_birthdate   (cdm_birthdate)               | FÖDELSEDATUM (FÖDELSEDATUM)                           |
| cdm_gender   (cdm_gender)                     | KÖN (KÖN)                                   |
| cdm_primaryaddress   (cdm_primaryaddress)     | PRIMARYCONTACTEMAIL   (PRIMARYCONTACTEMAIL )      |
| cdm_primarytelephone   (cdm_primarytelephone) | PRIMARYCONTACTPHONE   (PRIMARYCONTACTPHONE)       |
| cdm_facebookidentity   (cdm_facebookidentity) | PRIMARYCONTACTFACEBOOK   (PRIMARYCONTACTFACEBOOK) |
| cdm_twitteridentity   (cdm_twitteridentity)   | PRIMARYCONTACTTWITTER   (PRIMARYCONTACTTWITTER)   |
| cdm_linkedinIdentity   (cdm_linkedinIdentity) | PRIMARYCONTACTLINKEDIN   (PRIMARYCONTACTLINKEDIN) |
| cdm_websiteurl   (cdm_websiteurl)             | PRIMARYCONTACTURL   (PRIMARYCONTACTURL)           |
| cdm_firstname   (cdm_firstname)               | FIRSTNAME   (FIRSTNAME)                           |
| cdm_middlename   (cdm_middlename)             | MIDDLENAME   (MIDDLENAME)                         |
| cdm_lastname   (cdm_lastname)                 | LASTNAME (LASTNAME)                               |
| cdm_workernumber   (cdm_workernumber)         | PERSONNELNUMBER   (PERSONNELNUMBER)               |
| cdm_type (cdm_type)                           | WORKERTYPE   (WORKERTYPE)                         |
| cdm_state   (cdm_state)                       | WORKSTATUS   (WORKERSTATUS)                       |

### <a name="employments-to-employment"></a>Anställning till anställning

| Dataverse-register (källa)                             | Entiteten ekonomi (destination) |
|-----------------------------------------------------------------|---------------------------------------------|
| cdm_employmentstartdate   (cdm_employmentstartdate)             | EMPLOYMENTSTARTDATE   (EMPLOYMENTSTARTDATE) |
| cdm_employmentenddate   (cdm_employmentenddate)                 | EMPLOYMENTENDDATE   (EMPLOYMENTENDDATE)     |
| cdm_workertype   (cdm_workertype)                               | WORKERTYPE   (WORKERTYPE)                   |
| cdm_workerid.cdm_workernumber   (cdm_workerid.cdm_workernumber) | PERSONNELNUMBER   (PERSONNELNUMBER)         |
| cdm_companyid.cdm_companycode   (cdm_companyid.cdm_companycode) | LEGALENTITYID   (LEGALENTITYID)             |

### <a name="employments-to-employment-detail"></a>Anställning till anställningsdetalj

| Dataverse-register (källa)                             | Entiteten ekonomi (destination)   |
|-----------------------------------------------------------------|-----------------------------------------------|
| cdm_employmentstartdate   (cdm_employmentstartdate)             | EMPLOYMENTSTARTDATE   (EMPLOYMENTSTARTDATE)   |
| cdm_employmentenddate   (cdm_employmentenddate)                 | EMPLOYMENTENDDATE   (EMPLOYMENTENDDATE)       |
| cdm_validfrom   (giltigt från)                                    | VALIDFROM   (VALIDFROM)                       |
| cdm_validto (giltigt   till)                                        | VALIDTO (VALIDTO)                             |
| cdm_workerstartdate   (cdm_workerstartdate)                     | WORKERSTARTDATE   (WORKERSTARTDATE)           |
| cdm_lastdateworked   (cdm_lastdateworked)                       | LASTDATEWORKED   (LASTDATEWORKED)             |
| cdm_transitiondate   (cdm_transitiondate)                       | TRANSITIONDATE   (TRANSITIONDATE)             |
| cdm_employerunitofnotice   (cdm_employerunitofnotice)           | EMPLOYERUNITOFNOTICE   (EMPLOYERUNITOFNOTICE) |
| cdm_workerunitofnotice   (cdm_workerunitofnotice)               | WORKERUNITOFNOTICE   (WORKERUNITOFNOTICE)     |
| cdm_workerid.cdm_workernumber   (cdm_workerid.cdm_workernumber) | PERSONNELNUMBER   (PERSONNELNUMBER)           |
| cdm_companyid.cdm_companycode   (cdm_companyid.cdm_companycode) | LEGALENTITYID   (LEGALENTITYID)               |
| cdm_employernoticeamount   (cdm_employernoticeamount)           | EMPLOYERNOTICEAMOUNT   (EMPLOYERNOTICEAMOUNT) |
| cdm_workernoticeamount   (cdm_workernoticeamount )              | WORKERNOTICEAMOUNT   (WORKERNOTICEAMOUNT)     |

### <a name="position-worker-assignment-to-position-worker-assignments"></a>Befattningstilldelning för medarbetare till Befattningstilldelningar för medarbetare

| Dataverse-register (källa)                             | Entiteten ekonomi (destination)   |
|-----------------------------------------------------------------|-----------------------------------------------|
| cdm_workerid.cdm_workernumber   (cdm_workerid.cdm_workernumber) | PERSONNELNUMBER   (PERSONNELNUMBER)           |
| cdm_jobpositionnumber   (Jobbefattningsnummer)                   | POSITIONID(POSITIONID)                        |
| cdm_validfrom   (giltigt från)                                    | VALIDFROM   (VALIDFROM)                       |
| cdm_validto (giltigt till)                                        | VALIDTO (VALIDTO)                             |

### <a name="worker-addresses-to-worker-postal-address-v2"></a>Adress till medarbetare till postadress V2 till medarbetare

| Dataverse-register (källa)                             | Entiteten ekonomi (destination)   |
|-----------------------------------------------------------------|-----------------------------------------------|
| cdm_workerid.cdm_workernumber   (cdm_workerid.cdm_workernumber) | PERSONNELNUMBER   (PERSONNELNUMBER)           |
| cdm_addresstype   (cdm_addresstype)                             | ADDRESSLOCATIONROLES   (ADDRESSLOCATIONROLES) |
| cdm_line1   (cdm_line1)                                         | ADDRESSSTREET   (ADDRESSSTREET)               |
| cdm_city (cdm_city)                                             | ADDRESSCITY   (ADDRESSCITY)                   |
| cdm_stateorprovince   (cdm_stateorprovince)                     | ADDRESSSTATE   (ADDRESSSTATE)                 |
| cdm_postalcode   (cdm_postalcode)                               | ADDRESSZIPCODE(ADDRESSZIPCODE)                |
| cdm_countryregion   (cdm_countryregion)                         | ADDRESSCOUNTRYREGION(ADDRESSCOUNTRYREGION)    |
| cdm_addressnumber   (cdm_addressnumber)                         | ADDRESSLOCATIONID(ADDRESSLOCATIONID)          |
| cdm_ispreferred   (cdm_ispreferred)                             | ISPRIMARY   (ISPRIMARY)                       |
| cdm_county   (cdm_county)                                       | ADDRESSCOUNTYID(ADDRESSCOUNTYID)              |
| cdm_addresstype   (cdm_addresstype)                             | ADDRESSDESCRIPTION(ADDRESSDESCRIPTION)        |

## <a name="integration-considerations"></a>Hänsyn för integrering

Integrering från personal för ekonomi försöker matcha poster baserat på ID. Om posterna matchar kommer dataintegreraren att skriva över data i ekonomi över med värdena för personal. Det kan dock uppstå ett problem om logiskt är olika poster och samma ID genererades i personal eller ekonomi utifrån respektive nummerserie.

Det här problemet kan uppstå med **arbetare** som använder **personalnummer** för att göra matchningen och **befattningar**. I jobb används inte nummerserier. Om samma jobb-ID finns i både personal och ekonomi kommer informationen i personal att skriva över Dynamics 365 Finance-informationen. 

Om du vill undvika problem med dubbla ID kan du antingen lägga till ett prefix [nummerserien](/dynamics365/unified-operations/fin-and-ops/organization-administration/number-sequence-overview?toc=%2fdynamics365%2funified-operations%2ftalent%2ftoc.json), eller ställa in ett inledande nummer på nummerserien som ligger utanför det andra systemets intervall. 

Det plats-ID som används för arbetaradressen är inte en del av en nummerserie. När du integrerar en arbetaradress från personal till ekonomi, kan en adresspost skapas om det redan finns en postadress i ekonomi. 

I följande illustration visas ett exempel på en mallmappning i Dataintegrerare. 

![Mallmappning.](./media/IntegrationMapping.png)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
