---
title: Utbyggbarhet basuppräkning för kön
description: Den här artikeln innehåller en översikt över utökningsbarheten för basuppräkning av kön (enum).
author: twheeloc
ms.date: 05/23/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: HRMParameters, EssWorkspace
audience: Application User
ms.custom:
- "51941"
- intro-internal
ms.assetid: 2cfb061a-a616-4bf9-9d98-9cde00039eec
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-03-19
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 61a80c16d24d8fda264340d79ed393db3f635908
ms.sourcegitcommit: 1717ff6af1879c6f3a8360936c42ecf55f86acd0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/07/2022
ms.locfileid: "9749322"
---
# <a name="gender-base-enum-extensibility"></a>Utbyggbarhet basuppräkning för kön

Uppräkning **Kön** (enum) är nu utbyggbar. I den här artikeln beskrivs de ändringar som du måste göra i kodbasen om du tänker utöka uppräkningen **Kön**.

## <a name="gender-vs-hcmpersongender"></a>Kön kontra HcmPersonGender

Det finns två uppräkningar för könsvärden:

- **Kön** (programplattform)
- **HcmPersonGender** (PersonnelManagement)

Uppräkningen **Kön** används genomgående Microsoft Dynamics 365 Finance, där **HcmPersonGender** är specifikt för funktionen administration av mänskligt kapital (HCM). Om du använder HCM-funktionen och ändrar kön bör du göra samma ändringar i uppräkningen **Kön** bör du göra samma ändringar i **HcmPersonGender**. Om du till exempel lägger till **transperson** till uppräkningen **kön**, lägg till **transperson** till **HcmPersonGender** också.

## <a name="hcmpersongendertranformutil-class"></a>HcmPersonGenderTranformUtil (klass)

En ny klass för **HcmPersonGenderTranformUtil** har skapats för att översättning ska kunna tillåtas mellan de två basuppräkningarna. I denna klass finns det två metoder: **convertGenderToHcmPersonGender** och **convertHcmPersonGenderToGender**. Du bör skapa ett filnamnstillägg genom att använda **beslutskedja** eller **händelsehanterare** och utöka båda metoderna till att mappa nya värden som läggs till varje basuppräkning för kön.

## <a name="payrollstatewagetaxprepdp-class"></a>PayrollStateWageTaxPrepDP (klass)

**PayrollStateWageTaxPrepDP** är dataproviderklassen för rapporten **Förberedelse för statlig skatt för lön** SQL Server Reporting Services (SSRS). För USA finns det tre värden: **Maln**, **Kvinna** och **Ospecificerad**. I metoden **populatePayrollStateWageTaxPrepTmp** finns en switch-sats som används för att mappa värdet av enum **HcmPersonGender** till ett av dessa tre fält: **IsMale**, **IsFemale** eller **IsUnspecifiedGender**. Standardvärdet för switch-utdraget är **IsUnspecifiedGender**. Om du lägger till värden till **HcmPersonGender** enum för att kartlägga annorlunda måste du skapa ett tillägg genom att använda klassen **beslutskedja** över metoden **populatePayrollStateWageTaxPrepTmp** för att ändra värdet efter behov.

## <a name="smmoutlooksync_contact-class"></a>smmOutlookSync_Contact (klass)

Integrationsklassen **smmOutlookSync_Contact** länkar värden till och från **Outlook** och **Kontaktpersoner**. **Outlook** har stöd för tre värden: **Man**, **Kvinna** och **Ospecificerad**. Klassen har två metoder som kan hjälpa dig att mappa **Kön** till **OutlookGenders**. Standardmetoden är **NonSpecific/UnSpecified**. Om du skapar ytterligare värden för enum **Kön** bör du skapa ett tillägg med klassen **beslutskedja** över båda metoderna och mappa efter behov.
