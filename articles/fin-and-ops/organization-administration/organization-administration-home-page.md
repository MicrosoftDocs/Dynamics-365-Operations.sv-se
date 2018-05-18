---
title: Startsidan Organisationsadministration
description: "Det här avsnittet hänvisar till resurser som hjälper dig att använda Microsoft Dynamics 365 for Finance and Operations, Enterprise edition i organisationen."
author: sericks007
manager: AnnBe
ms.date: 08/18/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 20421
ms.assetid: 7aa24a03-d172-47e9-81f8-ebd39e80bc60
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: a2c1d846527eac4db0a043c7f1c51da0e73bd796
ms.contentlocale: sv-se
ms.lasthandoff: 03/26/2018

---

# <a name="organization-administration-home-page"></a>Startsidan Organisationsadministration

[!include [banner](../includes/banner.md)]

Detta avsnitt presenterar innehåll som hjälper avancerade användare och administratörer att konfigurera Microsoft Dynamics 365 for Finance and Operations. Innehållet hjälper dem att konfigurera systemet så att det arbetar snabbt och effektivt inom din organisation eller företag.

Stora delar av det innehåll som anges här avser funktioner i modulen **Organisationsadministration**. Det finns emellertid ett antal uppgifter, exempelvis att skapa och använda en bokföringsmall, som kan utföras i valfri modul i syfte att hjälpa din organisation att arbeta mer effektivt. 

<a name="number-sequences"></a>Nummerserier
----------------
Nummerserier används för att generera läsliga unika identifierare för huvuddataposter och transaktionsposter och som kräver identifierare. En huvuddatapost eller en transaktionspost som kräver en identifierare kallas för en *referens*. Innan du kan skapa nya poster för en referens, måste du ställa in en nummerserie och koppla den till referensen.

-   [Översikt över nummerserier](number-sequence-overview.md)
-   [Ställa in nummerserier med hjälp av en guide](tasks/set-up-number-sequences-wizard.md) (Uppgiftsguide)
-   [Ställa in enskilda nummerserier](tasks/set-up-number-sequences-individual-basis.md) (Uppgiftsguide)

## <a name="organizations"></a>Organisationer
En organisation är en grupp personer som arbetar tillsammans för att utföra ett arbete eller uppnå ett mål. Organisationshierarkier representerar relationerna mellan de organisationer som finns i företaget.

Innan du konfigurerar organisationer och organiationshierarkier i Finance and Operations, se till att du planerar hur din verksamhet ska utformas. Organisationsmodellen har en avsevärd effekt på implementeringen av Finance and Operations och på affärsprocesser.

-   [Organisationer och organisationshierarkier](organizations-organizational-hierarchies.md)
-   [Planera en organisationshierarki](plan-organizational-hierarchy.md)
-   [Skapa en organisationshierarki](tasks/create-organization-hierarchy.md) (Uppgiftsguide)
-   [Skapa en juridisk person för](tasks/create-legal-entity.md) (Uppgiftsguide)
-   [Skapa en driftenhet](tasks/create-operating-unit.md) (Uppgiftsguide)

## <a name="address-books"></a>Adressböcker
Den globala adressboken är en central förvaringsplats för viktiga data som måste lagras för alla interna och externa personer och organisationer som företaget interagerar med. Data kopplad till externa poster inkluderar den externa partens namn, adress och kontaktinformation. 

När du har skapat den globala adressboken, kan du skapa ytterligare adressböcker efter behov, till exempel en separat adressbok för varje företag i organisationen eller för varje affärsområde. 

-   [Global adressbok](overview-global-address-book.md)
-   [Planera hur du ska konfigurera den globala adressboken och ytterligare adressböcker](plan-configuration-global-address-book-additional-address-books.md)
- [Konfigurera den globala adressboken](tasks/configure-global-address-book.md)
-   [Frågor och svar om adressböcker](qa-address-books.md)


## <a name="workflow"></a>Arbetsflöde
Ett arbetsflöde är ett system som installeras tillsammans med Finance and Operations och som du kan använda för att skapa individuella arbetsflöden eller affärsprocesser. När du skapar ett arbetsflöde anger du hur ett dokument förflyttas genom systemet genom att visa vem som måste slutföra en uppgift, fatta ett beslut eller godkänna ett dokument. 

-   [Översikt över arbetsflöden](overview-workflow-system.md)
-   [Arbetsflödeselement](workflow-elements.md)
-   [Arbetsflödesåtgärder](workflow-actions.md)
-   [Skapa ett arbetsflöde](create-workflow.md)

## <a name="electronic-signatures"></a>Elektroniska signaturer
En elektronisk signatur bekräftar identiteten hos en person som ska påbörja eller godkänna en dataprocess. I vissa branscher är en elektronisk signatur lika juridiskt bindande som en handskriven signatur. Elektroniska signaturer är ett juridiskt krav för flera reglerade branscher som läkemedelsbranschen, livsmedelsbranschen, samt rymd- och försvarsbranschen.

I Finance and Operations kan du använda elektroniska signaturer för kritiska affärsprocesser. Vissa processer har inbyggda funktioner för elektronisk signatur. Du kan även skapa anpassade signaturkrav för alla databastabeller och fält.

-   [Översikt över elektroniska underskrifter](electronic-signature-overview.md)
-   [Ställa in elektroniska signaturer](tasks/set-up-electronic-signatures.md) (Uppgiftsguide)

## <a name="case-management"></a>Ärendehantering
Genom att planera, spåra och analysera ärenden kan du utveckla effektiva lösningar som kan användas för liknande ärenden. När exempelvis kundtjänstmedarbetare eller allmänkunniga inom personalavdelningen skapar ärenden, kan de hitta information i kunskapsbasartiklar som hjälper dem att arbeta med eller slutföra ett ärende mer effektivt. 

-   [Hantera ärenden – översikt](cases.md)
-   [Konfigurera ärendesäkerhet, processer och kategorier](plan-case-management.md)

## <a name="record-templates"></a>Postmallar
Bokföringsmallar hjälper dig att skapa poster snabbare. Du kan skapa en bokföringsmall så att fältvärden som ofta används inte måste anges explicit för varje enskild ny post. 

-   [Postmallar](record-templates.md)
- [Skapa en bokföringsmall som underlättar datainmatning](../../dev-itpro/data-entities/tasks/create-record-template-facilitate-data-entry.md) (uppgiftsguide)
- [Använd en bokföringsmall för att skapa en ny post](../../dev-itpro/data-entities/tasks/use-record-template-new-record.md) (uppgiftsguide)

## <a name="general-organization-administration"></a>Allmän organisationsadministration
-   [Ändra banner eller logotypen](../get-started/tasks/change-banner-or-logo.md) (Uppgiftsguide)
- [Konfigurera dokumenthantering](configure-document-management.md)
- [Konfigurera och skicka e-post](configure-email.md)
-   [Datum/tidsdata och tidszoner](date-time-zones.md)








