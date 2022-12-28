---
title: Konfigurera integrering med Dataverse-tabeller
description: I denna artikel beskrivs integreringen mellan Microsoft Dynamics 365 Human Resources och Dataverse.
author: anschmidt
ms.date: 12/06/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2022-12-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 63c25020b7026a76ecc6e2c3563f8299627ec8a8
ms.sourcegitcommit: bdee5e642d417a13abdb778c14ec5f2dbbf8dee7
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/09/2022
ms.locfileid: "9838633"
---
# <a name="configure-integration-with-dataverse-tables"></a>Konfigurera integration med Dataverse-tabeller

>[!Important]
>Funktionerna som anges i den här artikeln är för närvarande tillgängliga för Dynamics 365 Human Resources i infrastrukturen för ekonomi och drift. 


Om du vill integrera Microsoft Dynamics 365 Human Resources med Dataverse kan du använda [Dataintegrerare](/powerapps/administrator/data-integrator). Mallen personal till Dataverse gör det möjligt att flöda data för jobb, befattningar, arbetare och andra att personal till Dataverse och från Dataverse till personal och skapa skrivinformation i båda systemen.

## <a name="system-requirements-for-human-resources"></a>Systemkrav för personal

Integreringslösningen kräver följande versioner av personal och Dynamics 365 Finance: 

- Dynamics 365 Finance version 7.2 och senare
- Dynamics CRM-miljö där en databas har skapats och Dynamics 365-program är tillåtna

## <a name="template-and-tasks"></a>Mall och uppgifter

Följ dessa steg för att komma åt mallen Personal till Ekonomi.

1. Öppna [Power Apps administrationscenter](https://admin.powerapps.com/). 
2. Under din miljö väljer du **Dynamics 365-appar** och sedan **Appkälla** i verktygsfältet.
3. Om du vill installera mallen söker du efter "Dubbelriktad skrivning personal" eller går direkt till följande adress: <https://appsource.microsoft.com/product/dynamics-365/mscrm.hcm_dualwrite>.
3. När installationen är klar öppnar du Dynamics 365 Finance.
4. Öppna arbetsytan **Datahantering**. 
5. Välj **Dubbelriktad skrivning**. 
6. Följ processen för att koppla miljön till minst ett företag i organisationen. 
7. När du är klar med att ställa in en länk till din Dataverse-miljö väljer du **Använd lösning**. Lösningen tillämpas och mappningarna installeras i integrationsappen.

## <a name="template-mappings"></a>Mallmappningar

I följande mappningstabeller för mallar anger namnet på uppgiften de entiteter som används i varje program. Ekonomi till vänster och Dataverse till höger.

### <a name="bank-account-disbursements-dual-write-to-bank-account-disbursement"></a>Bankkontoutbetalning (dubbelriktad skrivning) till Bankkontoutbetalning

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| ACCOUNTIDENTIFICATIONID        | cdm\_bankaccountid.cdm\_accountidentification        |
| BELOPP                         | cdm\_amount                                         |
| PRIORITY                       | cdm\_disbursementpriority                           |
| ANSTÄLLNINGSNUMMER                | cdm\_bankaccountid.cdm\_workerid.cdm\_workernumber    |
| REMAINDER                      | cdm\_isremainder                                    |

### <a name="benefit-calculation-rate-detail-dual-write-to-benefit-calculation-rate-detail"></a>Tariff för förmånsberäkning för uppgift (dubbelriktad skrivning) för tariff för förmånsberäkning

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| CONTRIBUTIONMETHOD             | cdm\_contributionmethod                             |
| EFFECTIVE                      | cdm\_effective                                      |
| EMPLOYERCONTRIBUTION           | cdm\_employercontribution                           |
| EXPIRATION                     | cdm\_expiration                                     |
| WORKERDEDUCTION                | cdm\_workerdeduction                                |
| NAMN                           | cdm\_calculationrateid.cdm\_name                     |

### <a name="benefit-calculation-rate-header-to-benefit-calculation-rate"></a>Huvud för tariff för förmånsberäkning till tariff för förmånsberäkning

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| BESKRIVNING                    | cdm\_description                                    |
| NAMN                           | cdm\_name                                           |
| TIERTYPE                       | cdm\_tiertype                                       |

### <a name="benefit-option-to-benefit-option"></a>Förmånsalternativ till förmånsalternativ

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| ALLOWBENEFICIARYDESIGNATIONS   | cdm\_allowbeneficiarydesignations                   |
| ALLOWDEPENDENTCOVERAGE         | cdm\_allowdependentcoverage                         |
| BENEFITOPTIONID                | cdm\_name                                           |
| BESKRIVNING                    | cdm\_description                                    |
| ISWAIVE                        | cdm\_iswaived                                       |

### <a name="benefit-type-to-benefit-type"></a>Förmånstyp till förmånstyp

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| BENEFITTYPEID                  | cdm\_name                                           |
| CONCURRENTENROLLMENT           | cdm\_concurrentenrollment                           |
| BESKRIVNING                    | cdm\_description                                    |
| PAYROLLCATEGORY                | cdm\_payrollcategory                                |

### <a name="business-calendar-to-business-process-calendar"></a>Affärskalender till affärsprocesskalender

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| CALENDARID                     | cdm\_name                                           |
| NAMN                           | cdm\_calendarname                                   |
| STARTDATE                      | cdm\_startdate                                      |
| ENDDATE                        | cdm\_enddate                                        |
| ISOPENMONDAY                   | cdm\_ismondayopen                                   |
| ISOPENTUESDAY                  | cdm\_istuesdayopen                                  |
| ISOPENWEDNESDAY                | cdm\_iswednesdayopen                                |
| ISOPENTHURSDAY                 | cdm\_isthursdayopen                                 |
| ISOPENFRIDAY                   | cdm\_isfridayopen                                   |
| ISOPENSATURDAY                 | cdm\_issaturdayopen                                 |
| ISOPENSUNDAY                   | cdm\_issundayopen                                   |

### <a name="business-process-to-business-process-header"></a>Affärsprocess till affärsprocessrubrik

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| PROCESSID                      | cdm\_processid                                      |
| PROCESSTYPE                    | cdm\_processtype                                    |
| GENERICSUBTYPE                 | cdm\_genericsubtype                                 |
| NAMN                           | cdm\_name                                           |
| BESKRIVNING                    | cdm\_description                                    |
| STATUS                         | cdm\_status                                         |
| TARGETDATE                     | cdm\_targetdate                                     |
| STARTDATETIME                  | cdm\_startdatetime                                  |
| ENDDATETIME                    | cdm\_enddatetime                                    |
| RESOLVEDBYPERSONNELNUMBER      | cdm\_resolvedbyid.cdm\_workernumber                  |
| PROCESSOWNERPERSONNELNUMBER    | cdm\_processownerid.cdm\_workernumber                |
| SOURCETEMPLATENAME             | cdm\_sourcetemplateid.cdm\_name                      |
| SOURCETEMPLATEPROCESSTYPE      | cdm\_sourcetemplateid.cdm\_businessprocesstype       |
| SOURCETEMPLATEGENERICSUBTYPE   | cdm\_sourcetemplateid.cdm\_genericsubtype            |

### <a name="business-process-library-task-group-to-business-process-library-task-group"></a>Uppgiftsgrupp för affärsprocessbibliotek till uppgiftsgrupp för affärsprocessbibliotek

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| PROCESSTYPE                    | cdm\_processtype                                    |
| NAMN                           | cdm\_name                                           |
| BESKRIVNING                    | cdm\_description                                    |

### <a name="business-process-stage-to-business-process-stage"></a>Affärsprocessteg till affärsprocessteg

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| PROCESSTYPE                    | cdm\_businessprocesstype                            |
| NAMN                           | cdm\_name                                           |
| BESKRIVNING                    | cdm\_description                                    |
| SEQUENCENUMBER                 | cdm\_sequencenumber                                 |

### <a name="business-process-task-to-business-process-task"></a>Affärsprocessuppgift till Affärsprocessuppgift

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| BESKRIVNING                    | cdm\_description                                    |
| DUEDATE                        | cdm\_duedate                                        |
| TASKID                         | cdm\_taskid                                         |
| INSTRUCTIONS                   | cdm\_instructions                                   |
| COMPLETIONDATETIME             | cdm\_completiondatetime                             |
| ASSIGNMENTTYPE                 | cdm\_assignmenttype                                 |
| ISOPTIONAL                     | cdm\_isoptional                                     |
| NAMN                           | cdm\_name                                           |
| STATUS                         | cdm\_status                                         |
| RESOLVEDBY\_PERSONNELNUMBER     | cdm\_resolvedbyid.cdm\_workernumber                  |
| TEMPLATETASKID                 | cdm\_templatetaskid.cdm\_taskid                      |
| ASSIGNEDWORKER\_PERSONNELNUMBER | cdm\_assignedworkerid.cdm\_workernumber              |
| PROCESSID                      | cdm\_processheaderid.cdm\_processid                  |
| ASSIGNEDGROUP\_NAME             | cdm\_assignedgroupid.cdm\_name                       |
| ASSIGNEDPOSITION\_POSITIONID    | cdm\_assignedposition.cdm\_jobpositionnumber         |

### <a name="business-process-template-to-checklist-template-header"></a>Affärsprocessmall till Checklistemallens rubrik

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| PROCESSTYPE                    | cdm\_businessprocesstype                            |
| GENERICSUBTYPE                 | cdm\_genericsubtype                                 |
| NAMN                           | cdm\_name                                           |
| BESKRIVNING                    | cdm\_description                                    |
| CALENDARID                     | cdm\_businessprocesscalendarid.cdm\_name             |
| ANSTÄLLNINGSNUMMER                | cdm\_processownerid.cdm\_workernumber                |
| ISACTIVE                       | cdm\_isactive                                       |

### <a name="business-process-template-task-to-checklist-template-task"></a>Affärsprocessmalluppgift till Checklistemallens rubrikuppgift

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| TASKID                         | cdm\_taskid                                         |
| NAMN                           | cdm\_name                                           |
| TEMPLATEHEADER\_PROCESSTYPE     | cdm\_businessprocesstemplateheaderid.cdm\_businessprocesstype |
| TEMPLATEHEADER\_GENERICSUBTYPE  | cdm\_businessprocesstemplateheaderid.cdm\_genericsubtype |
| TEMPLATEHEADER\_NAME            | cdm\_businessprocesstemplateheaderid.cdm\_name       |
| BESKRIVNING                    | cdm\_description                                    |
| DUEDATEOFFSETDAYS              | cdm\_duedateoffsetdays                              |
| MENUITEMTYPE                   | cdm\_tasklinktype                                   |
| MENUITEM                       | cdm\_tasklink                                       |
| CONTACTPERSON\_PERSONNELNUMBER  | cdm\_contactpersonid.cdm\_workernumber               |
| ASSIGNMENTTYPE                 | cdm\_assignmenttype                                 |
| ASSIGNEDWORKER\_PERSONNELNUMBER | cdm\_assignedworkerid.cdm\_workernumber              |
| ASSIGNEDPOSITION\_POSITIONID    | cdm\_assignedpositionid.cdm\_jobpositionnumber       |
| ASSIGNEDGROUP\_NAME             | cdm\_assignedgroupid.cdm\_name                       |
| ISOPTIONAL                     | cdm\_isoptional                                     |
| INSTRUCTIONS                   | cdm\_instructions                                   |

### <a name="calculation-frequency-to-benefit-calculation-frequency"></a>Beräkningsfrekvens till beräkningsfrekvens för förmån

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| BESKRIVNING                    | cdm\_description                                    |
| FREKVENS                      | cdm\_name                                           |
| FREQUENCYCONTROL               | cdm\_frequencycontrol                               |
| ISIMMUTABLE                    | cdm\_isimmutable                                    |

### <a name="calculation-frequency-pay-period-to-benefit-calculation-frequency-pay-period"></a>Löneperiod med frekvens i beräkning till Frekvens i förmånsberäkning för löneperiod

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| CALCULATIONFREQUENCYID         | cdm\_benefitcalculationfrequencyid.cdm\_name         |
| PERIODSTARTDATE                | cdm\_payperiodid.cdm\_periodstartdate                |
| PAYCYCLEID                     | cdm\_payperiodid.cdm\_paycycleid.cdm\_name            |

### <a name="calendar-to-work-calendar"></a>Kalender till arbetskalender

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| CALENDARID                     | cdm\_name                                           |
| CALENDARNAME                   | cdm\_description                                    |
| WORKCALENDARHOLIDAYID          | cdm\_workcalendarholidayid.cdm\_name                 |

### <a name="compensation-fixed-action-table-to-fixed-compensation-event"></a>Fast kompensationsåtgärdsregister till fast kompensationshändelse

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| ACTION                         | cdm\_name                                           |
| ACTIVE                         | cdm\_isactive                                       |
| BESKRIVNING                    | cdm\_description                                    |
| TYP                           | cdm\_eventtype                                      |

### <a name="compensation-fixed-plan-to-compensation-fixed-plan"></a>Fast kompensationsplan till Fast kompensationsplan

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| PLAN                           | cdm\_name                                           |
| BESKRIVNING                    | cdm\_description                                    |
| TYP                           | cdm\_type                                           |
| EFFECTIVEDATE                  | cdm\_effectivedate                                  |
| EXPIRATIONDATE                 | cdm\_expirationdate                                 |
| VALUTA                       | cdm\_transactioncurrencyid.isocurrencycode          |
| PAYFREQUENCY                   | cdm\_payfrequency.cdm\_name                          |
| HIRERULE                       | cdm\_hirerule                                       |
| OUTOFRANGETOLERANCE            | cdm\_outofrangetolerance                            |
| RECOMMENDATIONALLOWED          | cdm\_recommendationallowed                          |
| COMPENSATIONSTRUCTURE          | cdm\_compensationgrid.cdm\_name                      |
| REFPOINTSETUPID                | cdm\_referencepointsetupline.cdm\_referencepointsetupid.cdm\_name |
| CONTROLPOINT                   | cdm\_referencepointsetupline.cdm\_name               |

### <a name="compensation-grids-to-compensation-grid"></a>Kompensationsrutnät till kompensationsrutnät

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| GRIDID                         | cdm\_name                                           |
| BESKRIVNING                    | cdm\_description                                    |
| EFFECTIVEDATE                  | cdm\_effectivedate                                  |
| EXPIRATIONDATE                 | cdm\_expirationdate                                 |
| REFERENCESETUP                 | cdm\_referencepointsetupid.cdm\_name                 |
| TYP                           | cdm\_type                                           |
| VALUTA                       | cdm\_transactioncurrencyid.isocurrencycode          |

### <a name="compensation-job-function-to-job-function"></a>Kompensationsjobbfunktion för jobbfunktion

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| JOBFUNCTIONID                  | cdm\_name                                           |
| BESKRIVNING                    | cdm\_description                                    |

### <a name="compensation-job-type-to-job-type"></a>Kompensationsjobbtyp för jobbtyp

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| JOBTYPEID                      | cdm\_name                                           |
| BESKRIVNING                    | cdm\_description                                    |
| EXEMPTSTATUS                   | cdm\_exemptstatus                                   |

### <a name="compensation-pay-frequency-to-compensation-pay-frequency"></a>Lönefrekvens för kompensation till Lönefrekvens för kompensation

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| PAYRATECONVERSION              | cdm\_name                                           |
| PERIOD                         | cdm\_period                                         |
| BESKRIVNING                    | cdm\_description                                    |
| ANNUALCONVERSIONFACTOR         | cdm\_annualconversionfactor                         |
| HOURLYCONVERSIONFACTOR         | cdm\_hourlyconversionfactor                         |
| MONTHLYCONVERSIONFACTOR        | cdm\_monthlyconversionfactor                        |
| WEEKLYCONVERSIONFACTOR         | cdm\_weeklyconversionfactor                         |

### <a name="compensation-regions-to-compensation-region"></a>Kompensationsregion till kompensationsregion

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| BESKRIVNING                    | cdm\_description                                    |
| PLATS                       | cdm\_name                                           |

### <a name="compensation-variable-plan-v2-to-compensation-variable-plan"></a>Variabel kompensationsplan V2 till Variabel kompensationsplan

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| VARIABLEAWARDBASIS             | cdm\_awardbasis                                     |
| AWARDBASISCALCULATION          | cdm\_awardbasiscalculation                          |
| CALCULATIONTYPE                | cdm\_calculationtype                                |
| BESKRIVNING                    | cdm\_description                                    |
| ENABLEENROLLMENT               | cdm\_enableenrollment                               |
| ENABLELEVELS                   | cdm\_enablelevels                                   |
| ENABLERECOMMENDATION           | cdm\_enablerecommendation                           |
| HIRERULE                       | cdm\_hirerule                                       |
| LEVERAGE100PERCENT             | cdm\_leverage100percent                             |
| LEVERAGEMAXIMUM                | cdm\_leveragemaximum                                |
| LEVERAGEMINIMUM                | cdm\_leverageminimum                                |
| LEVERAGEOVEROBJECTIVE          | cdm\_leverageoverobjective                          |
| LEVERAGEUNDEROBJECTIVE         | cdm\_leverageunderobjective                         |
| PERCENTOFBASIS                 | cdm\_percentofbasis                                 |
| PLANID                         | cdm\_name                                           |
| VARIABLECOMPENSATIONTYPE       | cdm\_variablecompensationtypeid.cdm\_name            |
| UNITCURRENCYCODE               | transactioncurrencyid.isocurrencycode              |
| UNITRELATIONSHIP               | cdm\_unitrelationship                               |
| UNITVALUE                      | cdm\_unitvalue                                      |
| NUMBEROFUNITSREAL              | cdm\_numberofunits                                  |
| EFFECTIVEDATE                  | cdm\_effectivedate                                  |
| EXPIRATIONDATE                 | cdm\_expirationdate                                 |
| VESTINGRULE                    | cdm\_vestingruleid.cdm\_name                         |
| LEVERAGETOLERANCEMAX           | cdm\_leveragetolerancemax                           |
| LEVERAGETOLERANCEMIN           | cdm\_leveragetolerancemin                           |

### <a name="compensation-variable-type-to-compensation-variable-plan-type"></a>Variabel kompensationstyp till Variabel kompensationsplantyp

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| BESKRIVNING                    | cdm\_description                                    |
| TYP                           | cdm\_awardtype                                      |
| VARIABLECOMPENSATIONTYPE       | cdm\_name                                           |

### <a name="compensation-vesting-rules-to-vesting-rule"></a>Överlåtelseregler för kompensation för överlåtelseregel

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| BESKRIVNING                    | cdm\_description                                    |
| NOTERING                           | cdm\_notes                                          |
| VESTINGRULE                    | cdm\_name                                           |

### <a name="department-v2-to-department"></a>Avdelning V2 till Avdelning

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| OPERATINGUNITNUMBER            | cdm\_departmentnumber                               |
| NAMN                           | cdm\_name                                           |
| SEARCHNAME                     | cdm\_description                                    |
| PARTYTYPE                      | cdm\_partytype                                      |

### <a name="dual-write-tax-region-to-tax-region"></a>Skatteregion för dubbelriktad skrivning till skatteregion

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| CITY                           | cdm\_city                                           |
| COUNTRYORREGION                | cdm\_countryorregion                                |
| COUNTY                         | cdm\_county                                         |
| STATE                          | cdm\_stateorprovince                                |
| TAXREGIONNAME                  | cdm\_name                                           |

### <a name="dual-write-worker-identification-to-worker-person-identification-number"></a>Dubbelriktad skrivning av medarbetares identifiering till Arbetsidentifieringsnummer

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| BESKRIVNING                    | cdm\_description                                    |
| ENTRYTYPE                      | cdm\_entrytype                                      |
| EXPIRATIONDATE                 | cdm\_expirationdate                                 |
| IDENTIFICATIONNUMBER           | cdm\_identificationnumber                           |
| IDENTIFICATIONTYPEID           | cdm\_identificationtypeid.cdm\_name                  |
| ISPRIMARY                      | cdm\_isprimary                                      |
| ISSUEDATE                      | cdm\_issuedate                                      |
| ISSUINGAGENCYID                | cdm\_issuingagencyid.cdm\_name                       |
| WORKERNUMBER                   | cdm\_workerid.cdm\_workernumber                      |

### <a name="compensation-structure-to-compensation-structure"></a>Kompensationsstruktur till kompensationsstruktur

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| BELOPP                         | cdm\_amount                                         |
| GRID                           | cdm\_compensationgridid.cdm\_name                    |
| LEVELID                        | cdm\_compensationlevelid.cdm\_name                   |
| REFERENCEPOINTLINENUMBER       | cdm\_referencepointid.cdm\_linenumber                |
| REFERENCESETUP                 | cdm\_referencepointid.cdm\_referencepointsetupid.cdm\_name |
| REFERENCEPOINT                 | cdm\_referencepointid.cdm\_name                      |

### <a name="earning-code-to-payroll-earning-code"></a>Inkomstkod till Inkomstkod

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| EARNINGCODE                    | cdm\_name                                           |
| BESKRIVNING                    | cdm\_description                                    |
| INCLUDEINPAYMENTTYPE           | cdm\_includeinpaymenttype                           |
| QUANTITYUNIT                   | cdm\_quantityunit                                   |
| TRACKFMLAHOURS                 | cdm\_trackfmlahours                                 |
| ISPRODUCTIVE                   | cdm\_isproductive                                   |

### <a name="employee-fixed-compensation-to-worker-fixed-compensation"></a>Medarbetarens fasta kompensation till Arbetarens fasta kompensation

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| COMPENSATIONLEVELID            | cdm\_compensationlevelid.cdm\_name                   |
| TYP                           | cdm\_compensationtype                               |
| EFFECTIVEDATE                  | cdm\_effectivedate                                  |
| EXPIRATIONDATE                 | cdm\_expirationdate                                 |
| LINENUMBER                     | cdm\_linenumber                                     |
| PAYFREQUENCY                   | cdm\_payfrequencyid.cdm\_name                        |
| PAYRATE                        | cdm\_payrate                                        |
| PLAN                           | cdm\_planid.cdm\_name                                |
| POSITIONID                     | cdm\_positionid.cdm\_jobpositionnumber               |
| PROCESSTYPE                    | cdm\_processtype                                    |
| ANSTÄLLNINGSNUMMER                | cdm\_workerid.cdm\_workernumber                      |
| ACTION                         | cdm\_eventid.cdm\_name                               |
| STEP                           | cdm\_referencepointsetuplineid.cdm\_name             |
| REFPOINTSETUPID                | cdm\_referencepointsetuplineid.cdm\_referencepointsetupid.cdm\_name |

### <a name="employment-per-company-to-employment"></a>Anställning per företag till Anställning

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| EMPLOYMENTENDDATE              | cdm\_employmentenddate                              |
| ANSTÄLLNINGSNUMMER                | cdm\_workerid.cdm\_workernumber                      |
| EMPLOYMENTSTARTDATE            | cdm\_employmentstartdate                            |
| WORKERTYPE                     | cdm\_workertype                                     |
| DIMENSIONDISPLAYVALUE          | cdm\_dimensiondisplayvalue                          |
| ADJUSTEDWORKERSTARTDATE        | cdm\_adjustedworkerstartdate                        |
| EMPLOYERNOTICEAMOUNT           | cdm\_employernoticeamount                           |
| EMPLOYERUNITOFNOTICE           | cdm\_employerunitofnotice                           |
| WORKERUNITOFNOTICE             | cdm\_workerunitofnotice                             |
| WORKERNOTICEAMOUNT             | cdm\_workernoticeamount                             |
| LASTDATEWORKED                 | cdm\_lastdateworked                                 |
| PROBATIONENDDATE               | cdm\_probationenddate                               |
| TRANSITIONDATE                 | cdm\_transitiondate                                 |
| TRANSITIONREASONCODENAME       | cdm\_transitionreasoncode.cdm\_name                  |
| WORKERSTARTDATE                | cdm\_workerstartdate                                |
| VALIDTO                        | cdm\_validto                                        |
| VALIDFROM                      | cdm\_validfrom                                      |

### <a name="ethnic-origins-to-ethnic-origin"></a>Etniskt ursprung till etniskt ursprung

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| ETHNICORIGINID                 | cdm\_name                                           |
| BESKRIVNING                    | cdm\_description                                    |

### <a name="group-assignment-to-business-process-group-assignment"></a>Grupptilldelning till Tilldelning av affärsprocessgrupp

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| NAMN                           | cdm\_name                                           |
| BESKRIVNING                    | cdm\_description                                    |
| ISACTIVE                       | cdm\_isactive                                       |

### <a name="identification-type-to-worker-person-identification-type"></a>Identifieringstyp till Typen för arbetarens identifieringstyp

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| BESKRIVNING                    | cdm\_description                                    |
| IDENTIFICATIONTYPEID           | cdm\_name                                           |
| ALLOWEDVALUES                  | cdm\_allowedvalues                                  |
| FIXEDLENGTH                    | cdm\_fixedlength                                    |
| IDENTIFICATIONNUMBERFORMAT     | cdm\_identificationnumberformat                     |

### <a name="issuing-agency-to-person-identification-issuing-agency"></a>Utfärdande organ till Utfärdande organ för personidentifiering

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| E-POST                          | cdm\_email                                          |
| EXTENSION                      | cdm\_extension                                      |
| FAX                            | cdm\_fax                                            |
| ISSUINGAGENCY                  | cdm\_name                                           |
| MOBILEPHONE                    | cdm\_mobilephone                                    |
| INTERNETADDRESS                | cdm\_websiteurl                                     |
| NAMN                           | cdm\_description                                    |
| PAGER                          | cdm\_pager                                          |
| SMS                            | cdm\_sms                                            |
| TELEPHONE                      | cdm\_telephone                                      |
| TELEXNUMBER                    | cdm\_telex                                          |
| ADDRESSCITY                    | cdm\_city                                           |
| ADDRESSCOUNTY                  | cdm\_county                                         |
| ADDRESSDESCRIPTION             | cdm\_addressdescription                             |
| ADDRESSSTATE                   | cdm\_stateorprovince                                |
| ADDRESSSTREET                  | cdm\_street                                         |
| ADDRESSZIPCODE                 | cdm\_postalcode                                     |
| ADDRESSCOUNTRYREGIONISOCODE    | cdm\_countryregion                                  |

### <a name="job-positions-dual-write-to-job-position"></a>Jobbefattningar med dubbelriktad skrivning till Jobbefattning

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| POSITIONID                     | cdm\_jobpositionnumber                              |
| ACTIVATION                     | cdm\_activation                                     |
| AVAILABLEFORASSIGNMENT         | cdm\_availableforassignment                         |
| COMPENSATIONREGIONID           | cdm\_compensationregionid.cdm\_name                  |
| DEPARTMENTID                   | cdm\_departmentid.cdm\_departmentnumber              |
| BESKRIVNING                    | cdm\_description                                    |
| FULLTIMEEQUIVALENT             | cdm\_fulltimeequivalent                             |
| JOBID                          | cdm\_jobid.cdm\_name                                 |
| PARENTPOSITIONID               | cdm\_parentjobpositionid.cdm\_jobpositionnumber      |
| POSITIONTYPEID                 | cdm\_positiontypeid.cdm\_name                        |
| PENSION                     | cdm\_retirement                                     |
| TITLEID                        | cdm\_titleid.cdm\_name                               |
| VALIDFROM                      | cdm\_validfrom                                      |
| VALIDTO                        | cdm\_validto                                        |

### <a name="jobs-dual-write-to-job"></a>Jobb dubbelriktad skrivning till Jobb

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| JOBID                          | cdm\_name                                           |
| BESKRIVNING                    | cdm\_description                                    |
| JOBDESCRIPTION                 | cdm\_jobdescription                                 |
| ALLOWUNLIMITEDPOSITIONS        | cdm\_allowunlimitedpositions                        |
| MAXIMUMNUMBEROFPOSITIONS       | cdm\_maximumnumberofpositions                       |
| JOBFUNCTIONID                  | cdm\_jobfunctionid.cdm\_name                         |
| JOBTYPEID                      | cdm\_jobtypeid.cdm\_name                             |
| TITLEID                        | cdm\_titleid.cdm\_name                               |
| VALIDFROM                      | cdm\_validfrom                                      |
| VALIDTO                        | cdm\_validto                                        |
| DEFAULTFULLTIMEEQUIVALENCY     | cdm\_defaultfulltimeequivalent                      |

### <a name="language-codes-to-language"></a>Språkkoder till Språk

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| LANGUAGECODEID                 | cdm\_name                                           |
| BESKRIVNING                    | cdm\_description                                    |

### <a name="leave-and-absence-bank-transaction-v2-to-leave-bank-transaction"></a>Transaktion för tjänstledighets- och frånvarobank V2 till Transaktion för tjänstledighetsbank

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| BELOPP                         | cdm\_amount                                         |
| LEAVETYPEID                    | cdm\_leavetypeid.cdm\_type                           |
| LEAVEPLANID                    | cdm\_leaveplanid.cdm\_name                           |
| TRANSACTIONDATE                | cdm\_transactiondate                                |
| TRANSACTIONNUMBER              | cdm\_transactionnumber                              |
| ANSTÄLLNINGSNUMMER                | cdm\_workerid.cdm\_workernumber                      |
| TRANSACTIONTYPE                | cdm\_transactiontype                                |

### <a name="leave-and-absence-enrollment-v2-to-leave-enrollment"></a>Anmälan om tjänstledighet och frånvaro V2 till Anmälning om tjänstledighet

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| STARTDATE                      | cdm\_startdate                                      |
| ENDDATE                        | cdm\_enddate                                        |
| CUSTOMDATE                     | cdm\_customdate                                     |
| ACCRUALSTARTDATE               | cdm\_accrualstartdate                               |
| ACCRUALDATEBASIS               | cdm\_accrualdatebasis                               |
| ISACCRUALSUSPENDED             | cdm\_isaccrualsuspended                             |
| LEAVEPLANID                    | cdm\_leaveplanid.cdm\_name                           |
| TIERBASIS                      | cdm\_tierbasis                                      |
| ANSTÄLLNINGSNUMMER                | cdm\_workerid.cdm\_workernumber                      |

### <a name="leave-and-absence-plan-v2-to-leave-plan"></a>Plan för tjänstledighet och frånvaro V2 till Tjänstledighetsplan

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| ACCRUALFREQUENCY               | cdm\_accrualfrequency                               |
| NAMN                           | cdm\_name                                           |
| BESKRIVNING                    | cdm\_description                                    |
| STARTDATE                      | cdm\_startdate                                      |
| LEAVETYPEID                    | cdm\_leavetypeid.cdm\_type                           |

### <a name="leave-and-absence-type-to-leave-type"></a>Typ av tjänstledighet och frånvaro till Tjänstledighetstyp

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| BESKRIVNING                    | cdm\_description                                    |
| TYP                           | cdm\_type                                           |
| EARNINGCODEID                  | cdm\_earningcodeid.cdm\_name                         |

### <a name="leave-and-absence-type-reason-code-to-leave-type-reason-code"></a>Orsakskod för tjänstledighets- och frånvarotyp till Ledighetstypens orsakskod

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| LEAVETYPE                      | cdm\_typeid.cdm\_type                                |
| REASONCODEID                   | cdm\_reasoncodeid.cdm\_name                          |

### <a name="leave-time-off-request-detail-to-leave-request-detail"></a>Information om ledighetsansökan till Information om begäran om tjänstledighet

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| BELOPP                         | cdm\_amount                                         |
| LEAVEDATE                      | cdm\_leavedate                                      |
| REQUESTID                      | cdm\_leaverequestid.cdm\_leaverequestnumber          |
| TYP                           | cdm\_leavetypeid.cdm\_type                           |

### <a name="leave-time-off-request-header-to-leave-request"></a>Huvud för ledighetsansökan till Begäran om tjänstledighet

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| REQUESTID                      | cdm\_leaverequestnumber                             |
| REQUESTDATE                    | cdm\_requestdate                                    |
| STATUS                         | cdm\_status                                         |
| COMMENT                        | cdm\_comment                                        |
| ANSTÄLLNINGSNUMMER                | cdm\_workerid.cdm\_workernumber                      |

### <a name="levels-to-compensation-level"></a>Nåvåer till Kompensationsnivå

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| TYP                           | cdm\_type                                           |
| BESKRIVNING                    | cdm\_description                                    |
| LEVEL                          | cdm\_name                                           |

### <a name="onboarding-process-header-to-onboard-process-header"></a>Rubriken Integrationsprocess till Rubriken Integrationsprocess

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| PROCESSID                      | cdm\_processheaderid.cdm\_processid                  |
| ONBOARDEDEMPLOYEEPERSONNELNUMBER | cdm\_onboardedemployeeid.cdm\_workernumber           |
| EMPLOYMENTPERSONNELNUMBER      | cdm\_employmentid.cdm\_workerid.cdm\_workernumber     |
| LEGALENTITYID                  | cdm\_employmentid.cdm\_companyid.cdm\_companycode     |
| EMPLOYMENTSTARTDATE            | cdm\_employmentid.cdm\_employmentstartdate           |

### <a name="pay-cycle-to-pay-cycle"></a>Lönecykel till Lönecykel

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| PAYCYCLEID                     | cdm\_name                                           |
| BESKRIVNING                    | cdm\_description                                    |
| PAYCYCLEFREQUENCY              | cdm\_frequency                                      |

### <a name="pay-period-to-pay-period"></a>Betalningsperiod till betalningsperiod

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| COMMENTS                       | cdm\_description                                    |
| DEFAULTPAYMENTDATE             | cdm\_defaultpaymentdate                             |
| PAYCYCLEID                     | cdm\_paycycleid.cdm\_name                            |
| PERIODENDDATE                  | cdm\_periodenddate                                  |
| PERIODSTARTDATE                | cdm\_periodstartdate                                |
| STATUS                         | cdm\_status                                         |

### <a name="payroll-details-for-positions-to-payroll-position-detail"></a>Löneuppgifter för positioner till Löneuppgift för befattning

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| PAYCYCLEID                     | cdm\_paycycle.cdm\_name                              |
| POSITIONID                     | cdm\_position.cdm\_jobpositionnumber                 |
| VALIDFROM                      | cdm\_validfrom                                      |
| VALIDTO                        | cdm\_validto                                        |
| ANNUALREGULARHOURS             | cdm\_annualregularhours                             |
| PAIDBYLEGALENTITY              | cdm\_paidby.cdm\_companycode                         |

### <a name="position-default-dimensions-dual-write-to-job-position-dimension"></a>Positionens standarddimensioner för dubbelriktad skrivning till Befattningsdimension

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| DIMENSIONDISPLAYVALUE          | cdm\_dimensiondisplayvalue                          |
| POSITIONID                     | cdm\_jobpositionid.cdm\_jobpositionnumber            |

### <a name="position-type-to-position-type"></a>Befattningstyp till befattningstyp

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| POSITIONTYPEID                 | cdm\_name                                           |
| BESKRIVNING                    | cdm\_description                                    |
| CLASSIFICATION                 | cdm\_classification                                 |

### <a name="position-worker-assignments-v2-to-position-worker-assignment"></a>Befattningstilldelning för medarbetare V2 till Befattningstilldelningar för medarbetare

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| ANSTÄLLNINGSNUMMER                | cdm\_workerid.cdm\_workernumber                      |
| POSITIONID                     | cdm\_jobpositionid.cdm\_jobpositionnumber            |
| VALIDFROM                      | cdm\_validfrom                                      |
| VALIDTO                        | cdm\_validto                                        |
| IsPrimaryPosition              | cdm\_isprimaryposition                              |

### <a name="reason-codes-to-reason-code"></a>Orsakskoder till orsakskod

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| REASONCODEID                   | cdm\_name                                           |
| BESKRIVNING                    | cdm\_description                                    |
| ISABSENCEAPPLICABLE            | cdm\_isabsenceapplicable                            |
| ISAPPLICATIONAPPLICABLE        | cdm\_isapplicationapplicable                        |
| ISCOMPENSATIONAPPLICABLE       | cdm\_iscompensationapplicable                       |
| ISCREATENEWPOSITIONAPPLICABLE  | cdm\_iscreatenewpositionapplicable                  |
| ISEDITPOSITIONAPPLICABLE       | cdm\_iseditpositionapplicable                       |
| ISHIREAPPLICABLE               | cdm\_ishireapplicable                               |
| ISSKILLMAPPINGAPPLICABLE       | cdm\_isskillmappingapplicable                       |
| ISTERMINATIONAPPLICABLE        | cdm\_isterminationapplicable                        |
| ISTRANSFERAPPLICABLE           | cdm\_istransferapplicable                           |

### <a name="reference-point-setup-line-dual-write-to-compensation-reference-point-setup-line"></a>Inställningsrad för referenspunkt (dubbelriktad skrivning) till Inställningsrad för kompensationsreferens

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| BESKRIVNING                    | cdm\_description                                    |
| LINENUM                        | cdm\_linenumber                                     |
| REFPOINTID                     | cdm\_name                                           |
| REFPOINTSETUPID                | cdm\_referencepointsetupid.cdm\_name                 |

### <a name="reference-point-setups-to-compensation-reference-point-setup"></a>Inställningar för referenspunkt till inställning för kompensationsreferens

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| REFERENCESETUP                 | cdm\_name                                           |
| BESKRIVNING                    | cdm\_description                                    |
| TYP                           | cdm\_compensationtype                               |

### <a name="skill-types-to-skill-type"></a>Färdighetstyper till färdighetstyp

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| SKILLTYPE                      | cdm\_name                                           |
| BESKRIVNING                    | cdm\_description                                    |

### <a name="titles-to-title"></a>Titlar till Titel

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| TITLEID                        | cdm\_name                                           |

### <a name="variable-compensation-level-v2-to-compensation-variable-plan-level"></a>Variabel kompensationsnivå V2 till Variabel kompensationsplannivå

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| AWARDAMOUNT                    | cdm\_awardamount                                    |
| AWARDPERCENT                   | cdm\_awardpercent                                   |
| AWARDUNITSREAL                 | cdm\_awardunits                                     |
| COMPENSATIONLEVELID            | cdm\_compensationlevelid.cdm\_name                   |
| PLANID                         | cdm\_compensationvariableplanid.cdm\_name            |

### <a name="veteran-status-to-veteran-status"></a>Veteranstatus till Veteranstatus

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| VETERANSTATUSID                | cdm\_name                                           |
| BESKRIVNING                    | cdm\_description                                    |
| ISPROTECTEDVETERAN             | cdm\_isprotectedveteran                             |

### <a name="work-calendar-enrollments-to-work-calendar-enrollment"></a>Anmälningar till arbetskalender för Anmälan till arbetskalender

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| STARTDATE                      | cdm\_employmentid.cdm\_employmentstartdate           |
| ANSTÄLLNINGSNUMMER                | cdm\_employmentid.cdm\_workerid.cdm\_workernumber     |
| CALENDARID                     | cdm\_workcalendarid.cdm\_name                        |
| COMPANYID                      | cdm\_employmentid.cdm\_companyid.cdm\_companycode     |

### <a name="work-calendar-holiday-to-work-calendar-holiday"></a>Helgdag i arbetskalender till Helgdag i arbetskalender

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| ID                             | cdm\_name                                           |
| BESKRIVNING                    | cdm\_description                                    |

### <a name="work-calendar-holiday-line-to-work-calendar-holiday-line"></a>Rad för helgdag i arbetskalender till Rad för helgdag i arbetskalender

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| HOLIDAYID                      | cdm\_workcalendarholidayid.cdm\_name                 |
| NAMN                           | cdm\_name                                           |
| HOLIDAYDATE                    | cdm\_holidaydate                                    |

### <a name="worker-to-worker"></a>Medarbetare till medarbetare

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| ANSTÄLLNINGSNUMMER                | cdm\_workernumber                                   |
| FIRSTNAME                      | cdm\_firstname                                      |
| mellannamn                     | cdm\_middlename                                     |
| LASTNAME                       | cdm\_lastname                                       |
| WORKERTYPE                     | cdm\_type                                           |
| WORKERSTATUS                   | cdm\_status                                         |
| PRIMARYCONTACTEMAIL            | cdm\_primaryemailaddress                            |
| PRIMARYCONTACTPHONE            | cdm\_primarytelephone                               |
| PRIMARYCONTACTFACEBOOK         | cdm\_facebookidentity                               |
| PRIMARYCONTACTTWITTER          | cdm\_twitteridentity                                |
| PRIMARYCONTACTLINKEDIN         | cdm\_linkedinidentity                               |
| PRIMARYCONTACTURL              | cdm\_websiteurl                                     |
| GENDER                         | cdm\_gender                                         |
| BIRTHDATE                      | cdm\_birthdate                                      |
| NAMN                           | cdm\_fullname                                       |

### <a name="worker-bank-accounts-to-worker-bank-account"></a>Bankkonton för arbetare till Bankkonton för arbetare

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| ACCOUNTIDENTIFICATION          | cdm\_accountidentification                          |
| ADDRESSCITY                    | cdm\_city                                           |
| ADDRESSCOUNTRYREGIONID         | cdm\_countryorregion                                |
| ADDRESSCOUNTY                  | cdm\_county                                         |
| ADDRESSDESCRIPTION             | cdm\_addressdescription                             |
| ADDRESSDISTRICTNAME            | cdm\_districtname                                   |
| ADDRESSPOSTBOX                 | cdm\_postofficebox                                  |
| ADDRESSSTATE                   | cdm\_stateorprovince                                |
| ADDRESSZIPCODE                 | cdm\_postalcode                                     |
| ANSTÄLLNINGSNUMMER                | cdm\_workerid.cdm\_workernumber                      |
| BANKACCOUNTNUMBER              | cdm\_bankaccountnumber                              |
| BANKACCOUNTTYPE                | cdm\_bankaccounttype                                |
| E-POST                          | cdm\_email                                          |
| EXTENSION                      | cdm\_extension                                      |
| FAX                            | cdm\_fax                                            |
| INTERNETADDRESS                | cdm\_websiteurl                                     |
| MOBILEPHONE                    | cdm\_mobilephone                                    |
| ROUTINGNUMBER                  | cdm\_routingnumber                                  |
| TELEPHONE                      | cdm\_telephone                                      |
| TELEXNUMBER                    | cdm\_telexnumber                                    |
| BANKIBAN                       | cdm\_iban                                           |
| SWIFTNO                        | cdm\_swiftcode                                      |
| BANKLOCATIONCODE               | cdm\_banklocationcode                               |
| BRANCHNAME                     | cdm\_branchname                                     |
| BRANCHNUMBER                   | cdm\_branchnumber                                   |
| ROUTINGNUMBERTYPE              | cdm\_routingnumbertype                              |
| ACCOUNTHOLDER                  | cdm\_accountholder                                  |
| NAMEOFPERSON                   | cdm\_nameofperson                                   |
| NAMN                           | cdm\_description                                    |
| ADDRESSSTREET                  | cdm\_line1                                          |
| ADDRESSSTREETNUMBER            | cdm\_line2                                          |

### <a name="worker-personal-details-to-worker-personal-detail"></a>Arbetarens personuppgifter till Arbetarens personuppgifter

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| ANSTÄLLNINGSNUMMER                | cdm\_workerid.cdm\_workernumber                      |
| BIRTHDATE                      | cdm\_birthdate                                      |
| PERSONBIRTHCITY                | cdm\_birthcity                                      |
| GENDER                         | cdm\_gender                                         |
| EXPATRIATEENDDATE              | cdm\_expatriateenddate                              |
| EXPATRIATESTARTDATE            | cdm\_expatriatestartdate                            |
| DISABLEDVETERAN                | cdm\_isdisabledveteran                              |
| DECEASEDDATE                   | cdm\_deceaseddate                                   |
| DISABLEDVERIFICATIONDATE       | cdm\_disabledveteranverificationdate                |
| EDUCATION                      | cdm\_education                                      |
| ETHNICORIGINID                 | cdm\_ethnicoriginid.cdm\_name                        |
| ISDISABLED                     | cdm\_isdisabled                                     |
| ISFULLTIMESTUDENT              | cdm\_isfulltimestudent                              |
| ISEXPATRIATERULINGAPPLICABLE   | cdm\_isexpatriaterulingapplicable                   |
| MARITALSTATUS                  | cdm\_maritalstatus                                  |
| MILITARYSERVICESTARTDATE       | cdm\_militaryservicestartdate                       |
| MILITARYSERVICEENDDATE         | cdm\_militaryserviceenddate                         |
| NUMBEROFDEPENDENTS             | cdm\_numberofdependents                             |
| NATIVELANGUAGEID               | cdm\_nativelanguageidid.cdm\_name                    |
| NATIONALITYCOUNTRYREGION       | cdm\_nationalitycountryregion                       |
| PERSONBIRTHCOUNTRYREGION       | cdm\_birthcountryregion                             |
| FATHERBIRTHCOUNTRYREGION       | cdm\_fatherbirthcountryregion                       |
| MOTHERBIRTHCOUNTRYREGION       | cdm\_motherbirthcountryregion                       |
| CITIZENSHIPCOUNTRYREGION       | cdm\_citizenshipcountryregion                       |
| VETERANSTATUSID                | cdm\_veteranstatusid.cdm\_name                       |

### <a name="worker-postal-addresses-dual-write-to-worker-address"></a>Arbetarens postadresser för dubbelriktad skrivning till Adress för arbetare

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| ANSTÄLLNINGSNUMMER                | cdm\_workerid.cdm\_workernumber                      |
| ADDRESSLOCATIONID              | cdm\_addressnumber                                  |
| ADDRESSLOCATIONROLES           | cdm\_addresstype                                    |
| EFFECTIVE                      | cdm\_effectivedate                                  |
| EXPIRATION                     | cdm\_expirationdate                                 |
| ADDRESSSTREET                  | cdm\_street                                         |
| ADDRESSSTREETNUMBER            | cdm\_streetnumber                                   |
| ADDRESSCITY                    | cdm\_city                                           |
| ADDRESSCOUNTRYREGIONISOCODE    | cdm\_countryregion                                  |
| ADDRESSSTATE                   | cdm\_stateorprovince                                |
| ADDRESSCOUNTYID                | cdm\_county                                         |
| ADDRESSDESCRIPTION             | cdm\_description                                    |
| ADDRESSLATITUDE                | cdm\_latitude                                       |
| ADDRESSLONGITUDE               | cdm\_longitude                                      |
| ADDRESSZIPCODE                 | cdm\_postalcode                                     |
| ADDRESSPOSTBOX                 | cdm\_postofficebox                                  |
| ISPRIMARY                      | cdm\_ispreferred                                    |

### <a name="working-time-to-work-calendar-time-interval"></a>Arbetstid till Tidsintervall till arbetskalendern

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| ENDTIME                        | cdm\_endtime                                        |
| STARTTIME                      | cdm\_starttime                                      |
| WORKCALENDARDATE               | cdm\_workcalendardayid.cdm\_calendardate             |
| WORKCALENDARID                 | cdm\_workcalendarid.cdm\_name                        |
| WORKCALENDARID                 | cdm\_workcalendardayid.cdm\_workcalendarid.cdm\_name  |

### <a name="working-times-to-work-calendar-day"></a>Arbetstider till Arbetsdagar i kalendern

| Entiteten ekonomi                 | Dataverse-tabell                                    | 
|--------------------------------|----------------------------------------------------|
| CALENDARDATE                   | cdm\_calendardate                                   |
| WORKCALENDARID                 | cdm\_workcalendarid.cdm\_name                        |
| WORKINGDAYDEFINITION           | cdm\_status                                         |

## <a name="integration-considerations"></a>Hänsyn för integrering

- Alla ändringar som görs i data i ett av systemet kommer att valideras av det andra systemet. Om ett fel inträffar skrivs inga data i något av systemet. 
- Alla skrivningar använder standardvärden för data (om anpassad logik inträffar i Ekonomi).
- Integreringsprogrammet med dubbelriktad skrivning använder integrationsnycklar för mappning mellan de två systemen. Ibland är det svårt att välja rätt integrationsnyckel, särskilt om flera integrationsnycklar uppfyller kraven. Nedan visas en lista över föreslagna integrationsnycklar för dina mappningar.

| Dataverse-tabell                          | Integreringsnycklar |
|------------------------------------------|------------------|
| Bankkontoutbetalningar                | cdm\_bankaccountid.cdm\_accountidentification, cdm\_bankaccountid.cdm\_workerid.cdm\_workernumber, cdm\_companyid.cdm\_companycode |
| Frekvens i förmånsberäkning            | cdm\_name |
| Löneperiod med frekvens i förmånsberäkning | cdm\_payperiodid.cdm\_periodstartdate, cdm\_payperiodid.cdm\_paycycleid.cdm\_name, cdm\_benefitcalculationfrequencyid.cdm\_name |
| Tariff för förmånsberäkning                 | cdm\_name |
| Uppgift om tariff för förmånsberäkning          | cdm\_workerdeduction, cdm\_effective, cdm\_calculationrateid.cdm\_name |
| Förmånsalternativ                           | cdm\_name |
| Förmånstyp                             | cdm\_name |
| Affärsprocesskalender                | cdm\_name |
| Tilldelning av affärsprocessgrupp        | cdm\_name |
| Affärsprocessrubrik                  | cdm\_processid |
| Affärsprocessbibliotekets uppgiftsgrupp      | cdm\_processtype, cdm\_name |
| Affärsprocessfas                   | cdm\_name, cdm\_businessprocesstype, cdm\_companyid.cdm\_companycode |
| Affärsprocessuppgift                    | cdm\_taskid |
| Affärsenhet                            | |
| Checklistemallens rubrik                | cdm\_businessprocesstype, cdm\_name, cdm\_genericsubtype |
| Checklistemallens uppgift                  | cdm\_taskid |
| Företag                                  | cdm\_companycode |
| Fast kompensationsplan                  | cdm\_name, cdm\_company.cdm\_companycode |
| Kompensationsrutnät                        | cdm\_name, cdm\_companyid.cdm\_companycode |
| Kompensationsnivå                       | cdm\_name |
| Lönefrekvens för kompensation               | cdm\_name, cdm\_companyid.cdm\_companycode |
| Kompensationsreferenspunkt       | cdm\_name, cdm\_companyid.cdm\_companycode |
| Ställ in kompensationsreferenspunkt  | cdm\_name, cdm\_referencepointsetupid.cdm\_name, cdm\_referencepointsetupid.cdm\_companyid.cdm\_companycode |
| Kompensationsregion                      | cdm\_name |
| Kompensationsstruktur                   | cdm\_compensationlevelid.cdm\_name, cdm\_referencepointid.cdm\_name, cdm\_referencepointid.cdm\_referencepointsetupid.cdm\_name, cdm\_referencepointid.cdm\_referencepointsetupid.cdm\_companyid.cdm\_companycode, cdm\_companyid.cdm\_companycode, cdm\_compensationgridid.cdm\_name, cdm\_compensationgridid.cdm\_companyid.cdm\_companycode |
| Variabel kompensationsplan               | cdm\_name, cdm\_companyid.cdm\_companycode |
| Variabel kompensationsplannivå         | cdm\_companyid.cdm\_companycode, cdm\_compensationvariableplanid.cdm\_name, cdm\_compensationvariableplanid.cdm\_companyid.cdm\_companycode, cdm\_compensationlevelid.cdm\_name |
| Typ av variabel kompensationsplan          | cdm\_name, cdm\_companyid.cdm\_companycode |
| Valuta                                 | isocurrencycode |
| Avdelning                               | cdm\_departmentnumber |
| Anställning                               | cdm\_employmentstartdate, cdm\_workerid.cdm\_workernumber, cdm\_companyid.cdm\_companycode |
| Etniskt ursprung                            | cdm\_name |
| Händelse för fast kompensation                 | cdm\_name, cdm\_companyid.cdm\_companycode |
| Befattning                                      | cdm\_name |
| Jobbfunktion                             | cdm\_name |
| Befattning                             | cdm\_jobpositionnumber |
| Befattningsdimension                   | cdm\_jobpositionid.cdm\_jobpositionnumber, cdm\_companyid.cdm\_companycode |
| Jobbtyp                                 | cdm\_name |
| Språk                                 | cdm\_name |
| Transaktion för tjänstledighetsbank                   | cdm\_transactiondate, cdm\_transactiontype, cdm\_transactionnumber, cdm\_leavetypeid.cdm\_type, cdm\_leavetypeid.cdm\_companyid.cdm\_companycode, cdm\_companyid.cdm\_companycode, cdm\_workerid.cdm\_workernumber |
| Anmälning om tjänstledighet                         | cdm\_startdate, cdm\_leaveplanid.cdm\_name, cdm\_leaveplanid.cdm\_companyid.cdm\_companycode, cdm\_companyid.cdm\_companycode, cdm\_workerid.cdm\_workernumber |
| Tjänstledighetsplan                               | cdm\_name, cdm\_companyid.cdm\_companycode |
| Begäran om tjänstledighet                            | cdm\_leaverequestnumber, cdm\_companyid.cdm\_companycode |
| Information om att lämna begäran                     | cdm\_leavedate, cdm\_leavetypeid.cdm\_type, cdm\_leavetypeid.cdm\_companyid.cdm\_companycode, cdm\_leaverequestid.cdm\_leaverequestnumber, cdm\_leaverequestid.cdm\_companyid.cdm\_companycode |
| Tjänstledighetstyp                               | cdm\_type, cdm\_companyid.cdm\_companycode |
| Ledighetstypens orsakskod                   | cdm\_reasoncodeid.cdm\_name, cdm\_typeid.cdm\_type, cdm\_typeid.cdm\_companyid.cdm\_companycode |
| Introduktionsprocessrubrik                   | cdm\_processheaderid.cdm\_processid |
| Organisation                             | |
| Lönecykel                                | cdm\_name |
| Löneperiod                               | cdm\_periodstartdate, cdm\_paycycleid.cdm\_name, cdm\_periodenddate |
| Inkomstkod                     | cdm\_name |
| Löneuppgift för befattning                  | cdm\_validfrom, cdm\_validto, cdm\_position.cdm\_jobpositionnumber |
| Utfärdande organ för personidentifiering     | cdm\_name |
| Befattningstyp                            | cdm\_name |
| Befattningstilldelning för medarbetare               | cdm\_validfrom, cdm\_jobpositionid.cdm\_jobpositionnumber |
| Orsakskod                              | cdm\_name |
| Kompetenstyp                               | cdm\_name |
| Skatteregion                               | cdm\_stateorprovince, cdm\_name, cdm\_countryorregion, cdm\_county, cdm\_city |
| Team                                     | azureactivedirectoryobjectid, membershiptype |
| Titel                                    | cdm\_name |
| Användare                                     | azureactivedirectoryobjectid |
| Överlåtelseregel                             | cdm\_name, cdm\_companyid.cdm\_companycode |
| Veteranstatus                           | cdm\_name |
| Arbetskalender                            | cdm\_name, cdm\_companyid.cdm\_companycode |
| Arbetsdagar i kalendern                        | cdm\_calendardate, cdm\_companyid.cdm\_companycode, cdm\_workcalendarid.cdm\_name, cdm\_workcalendarid.cdm\_companyid.cdm\_companycode |
| Anmälan till arbetskalender                 | cdm\_employmentid.cdm\_employmentstartdate, cdm\_employmentid.cdm\_workerid.cdm\_workernumber, cdm\_employmentid.cdm\_companyid.cdm\_companycode |
| Helgdag i arbetskalender                    | cdm\_name |
| Arbetskalenderns datumrad               | cdm\_holidaydate, cdm\_workcalendarholidayid.cdm\_name |
| Tidsintervall till arbetskalendern              | cdm\_starttime, cdm\_workcalendardayid.cdm\_calendardate, cdm\_workcalendardayid.cdm\_companyid.cdm\_companycode, cdm\_workcalendardayid.cdm\_workcalendarid.cdm\_name, cdm\_workcalendardayid.cdm\_workcalendarid.cdm\_companyid.cdm\_companycode, cdm\_companyid.cdm\_companycode, cdm\_workcalendarid.cdm\_name, cdm\_workcalendarid.cdm\_companyid.cdm\_companycode |
| Arbetare                                   | cdm\_workernumber |
| Adress för arbetare                           | cdm\_addressnumber, cdm\_addresstype, cdm\_workerid.cdm\_workernumber |
| Bankkonto för arbetare                      | cdm\_accountidentification, cdm\_workerid.cdm\_workernumber |
| Arbetarens fasta kompensation                | cdm\_linenumber, cdm\_effectivedate, cdm\_companyid.cdm\_companycode, cdm\_positionid.cdm\_jobpositionnumber, cdm\_workerid.cdm\_workernumber, cdm\_eventid.cdm\_name, cdm\_eventid.cdm\_companyid.cdm\_companycode, cdm\_planid.cdm\_name, cdm\_planid.cdm\_company.cdm\_companycode |
| Arbetsidentifieringsnummer      | cdm\_identificationnumber, cdm\_workerid.cdm\_workernumber, cdm\_identificationtypeid.cdm\_name |
| Arbetsidentifieringstyp        | cdm\_name |
| Arbetarens personuppgift                   | cdm\_workerid.cdm\_workernumber |
