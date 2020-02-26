---
title: Konfigurera integration med Finance
description: I den här artikeln beskrivs vilka funktioner som är tillgängliga för integration från Dynamics 365 Human Resources och Dynamics 365 Finance.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2e7070f627654c9eb889f3e0ee27e37681db0502
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010571"
---
# <a name="configure-integration-with-finance"></a>Konfigurera integration med Finance

I den här artikeln beskrivs vilka funktioner som är tillgängliga för integration från Dynamics 365 Human Resources och Dynamics 365 Finance. Mallen Personal till ekonomi som finns med [Dataintegrerare](https://docs.microsoft.com/powerapps/administrator/data-integrator) möjliggör flöde av data för jobb, positioner och arbetare. Uppgifterna flödar från personal till ekonomi. Mallen ger inte möjlighet för data att flöda tillbaka från ekonomi till personal. 

![Personal till ekonomi integrationsflöde](./media/TalentFinOpsFlow.png)

Lösningen personal till ekonomi innehåller följande typer av datasynkronisering. 

- Underhåll jobb i personal och synkronisera dem från personal till ekonomi.
- Underhåll positioner och positionstilldelningar i personal och synkronisera dem från personal till ekonomi.
- Underhåll anställningar i personal och synkronisera dem från personal till ekonomi.
- Underhåll arbetare och arbetaradresser i personal och synkronisera dem från personal till ekonomi.

## <a name="system-requirements-for-human-resources"></a>Systemkrav för personal
Integreringslösningen kräver följande versioner av personal och ekonomi: 
- Dynamics 365 Human Resources för Common Data Service.
- Dynamics 365 Finance version 7.2 och senare.

## <a name="template-and-tasks"></a>Mall och uppgifter

Gör följande om du vill öppna formuläret.
1. Öppna [Power Apps administrationscenter](https://admin.powerapps.com/). 
1. Välj **projekt** och i det övre högra hörnet väljer du **nytt projekt** för att välja allmänna mallar. Ett nytt projekt måste skapas för varje juridisk person som du vill integrera i i ekonomi.

Följande mall används för att synkronisera poster från personal till ekonomi.

- **Namn på mallen i dataintegration:** personal (personal Common Data Service till ekonomi)

  > [!NOTE]
  > Namnet på uppgiften innehåller de entiteter som används i varje program. Källan (personal) ligger till vänster och destinationen (Finance and Operations) är till höger.

Följande underliggande uppgifter används för att synkronisera poster från personal till ekonomi.
- Jobbfunktioner för kompensationsjobbfunktion
- Avdelningar till driftenhet
- Jobbtyper för kompensationsjobbtyp
- Jobb till jobb
- Jobb till jobbdetalj
- Befattningstyper till befattningstyp
- Jobbefattningar till grundläggande befattning
- Jobbefattningar till befattningsdetaljer
- Jobbefattningar till befattningstidslängd
- Jobbefattningar till befattningshierarkier
- Arbetare till arbetare
- Anställning till anställning
- Anställning till anställningsdetalj
- Befattningstilldelning för arbetare till Befattningstilldelningar för arbetare
- Adress till arbetare till postadress V2 till arbetare

## <a name="template-mappings"></a>Mallmappningar

### <a name="job-functions-to-compensation-job-function"></a>Jobbfunktioner för kompensationsjobbfunktion

| Common Data Service enhet (källa)                 | Finance and Operations enhet (destination) |
|-------------------------------------|---------------------------------------------|
| cdm_name (cdm_Job   Funktionsnamn)  | JOBFUNCTIONID   (JOBFUNCTIONID)            |
| cdm_description   (cdm_description) | BESKRIVNING   (BESKRIVNING)                 |

### <a name="departments-to-operating-unit"></a>Avdelningar till driftenhet

| Common Data Service enhet (källa)                           | Finance and Operations enhet (destination) |
|-----------------------------------------------|---------------------------------------------|
| cdm_name (cdm_name)                           | NAME (NAME)                                 |
| cdm_departmentnumber   (cdm_departmentnumber) | OPERATINGUNITNUMBER   (OPERATINGUNITNUMBER) |
|                                               | OPERATINGUNITTYPE   (OPERATINGUNITTYPE)     |
| cdm_description   (cdm_description)           | NAMEALIAS   (NAMEALIAS)                     |

### <a name="job-types-to-compensation-job-type"></a>Jobbtyper för kompensationsjobbtyp

| Common Data Service enhet (källa)                   | Finance and Operations enhet (destination) |
|---------------------------------------|---------------------------------------------|
| cdm_name (cdm_name)                   | JOBTYPEID   (JOBTYPEID)                     |
| cdm_description   (cdm_description)   | BESKRIVNING   (BESKRIVNING)                 |
| cdm_exemptstatus   (cdm_exemptstatus) | EXEMPTSTATUS   (EXEMPTSTATUS)               |

### <a name="jobs-to-jobs"></a>Jobb till jobb

| Common Data Service enhet (källa)                                           | Finance and Operations enhet (destination)           |
|---------------------------------------------------------------|-------------------------------------------------------|
| cdm_name (cdm_name)                                           | JOBID (JOBID)                                         |
| cdm_maximumnumberofpositions   (cdm_maximumnumberofpositions) | MAXIMUMNUMBEROFPOSITIONS   (MAXIMUMNUMBEROFPOSITIONS) |
| cdm_allowedunlimitedpositions   (cdm_allowunlimitedpositions) | ALLOWUNLIMITEDPOSITIONS   (ALLOWUNLIMITEDPOSITIONS)   |
| cdm_description   (cdm_description)                           | BESKRIVNING   (BESKRIVNING)                           |
| cdm_jobdescription   (cdm_jobdescription)                     | JOBDESCRIPTION   (JOBDESCRIPTIONS)                    |

### <a name="jobs-to-job-detail"></a>Jobb till jobbdetalj

| Common Data Service enhet (källa)                                             | Finance and Operations enhet (destination) |
|-----------------------------------------------------------------|---------------------------------------------|
| cdm_name (cdm_name)                                             | JOBID (JOBID)                               |
| cdm_jobtypeid.cdm_name   (Jobbtyp (jobbtypnamn))             | JOBTYPEID   (JOBTYPEID)                     |
| cdm_jobfunctionid.cdm_name   (Jobbfunktion (jobbfunktionsnamn)) | FUNCTIONID   (FUCNTIONID)                   |
| cdm_validfrom   (giltigt från)                                    | VALIDFROM   (VALIDFROM)                     |
| cdm_validto (giltigt till)                                        | VALIDTO (VALIDTO)                           |
| cdm_defaultfulltimeequivalent   (Heltidslön)   | FULLTIMEEQUIVALENT   (FULLTIMEEQUIVALENT)   |

### <a name="position-types-to-position-type"></a>Befattningstyper till befattningstyp

| Common Data Service enhet (källa)                       | Finance and Operations enhet (destination) |
|-------------------------------------------|---------------------------------------------|
| cdm_name (cdm_name)                       | POSITIONTYPEID   (POSITIONTYPEID)           |
| cdm_description   (cdm_description)       | BESKRIVNING   (BESKRIVNING)                 |
| cdm_classification   (cdm_classification) | KLASSIFICERING   (KLASSIFICERING)           |

### <a name="job-positions-to-base-position"></a>Jobbefattningar till grundläggande befattning

| Common Data Service enhet (källa)                           | Finance and Operations enhet (destination) |
|-----------------------------------------------|---------------------------------------------|
| cdm_jobpositionnumber   (Jobbefattningsnummer) | POSITIONID (POSITIONID)                      |

### <a name="job-positions-to-position-details"></a>Jobbefattningar till befattningsdetaljer

| Common Data Service enhet (källa)                                                      | Finance and Operations enhet (destination)       |
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

| Common Data Service enhet (källa)                             | Finance and Operations enhet (destination) |
|-------------------------------------------------|---------------------------------------------|
| cdm_jobpositionnumber   (Jobbefattningsnummer)   | POSITIONID (POSITIONID)                      |
| Beräknad     aktivering (beräknad aktivering) | VALIDFROM (VALIDFROM)                        |
| Beräknad     Pension (beräknad pension) | VALIDTO (VALIDTO)                         |

### <a name="job-positions-to-position-hiearchies"></a>Jobbefattningar till befattningshierarkier

| Common Data Service enhet (källa)                                                                           | Finance and Operations enhet (destination) |
|-----------------------------------------------------------------------------------------------|---------------------------------------------|
| cdm_jobpositionnumber   (Jobbefattningsnummer)                                                 | POSITIONID(POSITIONID)                      |
| cdm_parentjobpositionid.cdmjobpositionnumber   (cdm_parentjobpositionid.cdmjobpositionnumber) | PARENTPOSITIONID (PARENTPOSITIONID)         |
| cdm_validfrom   (giltigt från)                                                                  | VALIDFROM   (VALIDFROM)                     |
| cdm_validto (giltigt   till)                                                                      | VALIDTO (VALIDTO)                           |
| HIERARCHYTYPENAME   (HIERARCHYTYPENAME)                                                       | HIERARCHYTYPENAME   (HIERARCHYTYPENAME)     |


### <a name="workers-to-worker"></a>Arbetare till arbetare
| Common Data Service enhet (källa)                           | Finance and Operations enhet (destination)       |
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

| Common Data Service enhet (källa)                                             | Finance and Operations enhet (destination) |
|-----------------------------------------------------------------|---------------------------------------------|
| cdm_employmentstartdate   (cdm_employmentstartdate)             | EMPLOYMENTSTARTDATE   (EMPLOYMENTSTARTDATE) |
| cdm_employmentenddate   (cdm_employmentenddate)                 | EMPLOYMENTENDDATE   (EMPLOYMENTENDDATE)     |
| cdm_workertype   (cdm_workertype)                               | WORKERTYPE   (WORKERTYPE)                   |
| cdm_workerid.cdm_workernumber   (cdm_workerid.cdm_workernumber) | PERSONNELNUMBER   (PERSONNELNUMBER)         |
| cdm_companyid.cdm_companycode   (cdm_companyid.cdm_companycode) | LEGALENTITYID   (LEGALENTITYID)             |

### <a name="employments-to-employment-detail"></a>Anställning till anställningsdetalj

| Common Data Service enhet (källa)                                             | Finance and Operations enhet (destination)   |
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

### <a name="position-worker-assignment-to-position-worker-assignments"></a>Befattningstilldelning för arbetare till Befattningstilldelningar för arbetare

| Common Data Service enhet (källa)                                             | Finance and Operations enhet (destination)   |
|-----------------------------------------------------------------|-----------------------------------------------|
| cdm_workerid.cdm_workernumber   (cdm_workerid.cdm_workernumber) | PERSONNELNUMBER   (PERSONNELNUMBER)           |
| cdm_jobpositionnumber   (Jobbefattningsnummer)                   | POSITIONID(POSITIONID)                        |
| cdm_validfrom   (giltigt från)                                    | VALIDFROM   (VALIDFROM)                       |
| cdm_validto (giltigt   till)                                        | VALIDTO (VALIDTO)                             |

### <a name="worker-addresses-to-worker-postal-address-v2"></a>Adress till arbetare till postadress V2 till arbetare

| Common Data Service enhet (källa)                                             | Finance and Operations enhet (destination)   |
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

## <a name="integration-considerations"></a>Hänsyn för integration
När du integrerar data från personal för ekonomi kommer integrationen att försöka matcha poster baserat på ID. Om matchningen inträffar kommer data i ekonomi över med värdena för personal. Det kan dock uppstå ett problem om logiskt är olika poster och samma ID genererades i personal eller ekonomi utifrån respektive nummerserie.

De områden där detta kan inträffa är arbetare, som använder personalnummer för att göra matchningen och befattningar. I jobb används inte nummerserier. Om samma jobb-ID finns i både personal och ekonomi kommer informationen i personal att skriva över Dynamics 365 Finance informationen. 

Om du vill undvika problem med dubbla ID kan du antingen lägga till ett prefix [nummerserien](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/organization-administration/number-sequence-overview?toc=/dynamics365/unified-operations/talent/toc.json), eller ställa in ett inledande nummer på nummerserien som ligger utanför det andra systemets intervall. 

Det plats-ID som används för arbetaradressen är inte en del av en nummerserie. När du integrerar en arbetaradress från personal till ekonomi, kan en adresspost skapas om det redan finns en postadress i ekonomi. 

I följande illustration visas ett exempel på en mallmappning i Dataintegrerare. 

![Mallmappning](./media/IntegrationMapping.png)


