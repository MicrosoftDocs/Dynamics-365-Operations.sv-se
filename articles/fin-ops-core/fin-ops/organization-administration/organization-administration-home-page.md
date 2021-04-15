---
title: Organisationsadministration – startsida
description: Det här avsnittet hänvisar till resurser som hjälper dig i din organisation.
author: sericks007
ms.date: 08/18/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 20421
ms.assetid: 7aa24a03-d172-47e9-81f8-ebd39e80bc60
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0b9e69db0cd5533f52243e6d22110f9acc66b589
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5747671"
---
# <a name="organization-administration-home-page"></a>Organisationsadministration – startsida

[!include [banner](../includes/banner.md)]

Det här avsnittet innehållet som hjälper privilegierade användare och administratörer att konfigurera systemet så att det arbetar snabbt och effektivt inom din organisation eller företag.

Stora delar av det innehåll som anges här avser funktioner i modulen **Organisationsadministration**. Det finns emellertid ett antal uppgifter, exempelvis att skapa och använda en bokföringsmall, som kan utföras i valfri modul i syfte att hjälpa din organisation att arbeta mer effektivt.

## <a name="number-sequences"></a>Nummerserier

Nummerserier används för att generera läsliga unika identifierare för huvuddataposter och transaktionsposter och som kräver identifierare. En huvuddatapost eller en transaktionspost som kräver en identifierare kallas för en *referens*. Innan du kan skapa nya poster för en referens, måste du ställa in en nummerserie och koppla den till referensen.

- [Nummerserier – översikt](number-sequence-overview.md)
- [Ställa in nummerserier med hjälp av en guide](tasks/set-up-number-sequences-wizard.md) (Uppgiftsguide)
- [Ställa in enskilda nummerserier](tasks/set-up-number-sequences-individual-basis.md) (Uppgiftsguide)

## <a name="organizations"></a>Organisationer

En organisation är en grupp personer som arbetar tillsammans för att utföra ett arbete eller uppnå ett mål. Organisationshierarkier representerar relationerna mellan de organisationer som finns i företaget.

Innan du ställer in organisationer och organisationshierarkier måste du planera hur din verksamhet ska se ut. Organisationsmodellen har en viktig effekt på implementering och affärsprocesser.

- [Organisationer och organisationshierarkier – översikt](organizations-organizational-hierarchies.md)
- [Planera en organisationshierarki](plan-organizational-hierarchy.md)
- [Skapa en organisationshierarki](tasks/create-organization-hierarchy.md) (Uppgiftsguide)
- [Skapa en juridisk person för](tasks/create-legal-entity.md) (Uppgiftsguide)
- [Skapa en driftenhet](tasks/create-operating-unit.md) (Uppgiftsguide)

## <a name="address-books"></a>Adressböcker

Den globala adressboken är en central förvaringsplats för viktiga data som måste lagras för alla interna och externa personer och organisationer som företaget interagerar med. Data kopplad till externa poster inkluderar den externa partens namn, adress och kontaktinformation.

När du har skapat den globala adressboken, kan du skapa ytterligare adressböcker efter behov, till exempel en separat adressbok för varje företag i organisationen eller för varje affärsområde.

- [Översikt över global adressbok](overview-global-address-book.md)
- [Planera för den globala adressboken och andra adressböcker](plan-configuration-global-address-book-additional-address-books.md)
- [Konfigurera den globala adressboken](tasks/configure-global-address-book.md)
- [Vanliga frågor och svar om adressböcker](qa-address-books.md)

## <a name="workflow"></a>Arbetsflöde

Arbetsflöde är ett system som innehåller funktioner som du kan använda när du vill skapa individuella arbetsflöden eller affärsprocesser. När du skapar ett arbetsflöde anger du hur ett dokument förflyttas genom systemet genom att visa vem som måste slutföra en uppgift, fatta ett beslut eller godkänna ett dokument.

- [Arbetsflödessystem – översikt](overview-workflow-system.md)
- [Arbetsflödeselement](workflow-elements.md)
- [Åtgärder i godkännandeprocesser i ett arbetsflöde](workflow-actions.md)
- [Skapa arbetsflöden – översikt](create-workflow.md)

## <a name="electronic-signatures"></a>Elektroniska signaturer

En elektronisk signatur bekräftar identiteten hos en person som ska påbörja eller godkänna en dataprocess. I vissa branscher är en elektronisk signatur lika juridiskt bindande som en handskriven signatur. Elektroniska signaturer är ett juridiskt krav för flera reglerade branscher som läkemedelsbranschen, livsmedelsbranschen, samt rymd- och försvarsbranschen.

Du kan använda elektroniska signaturer för kritiska affärsprocesser. Vissa processer har inbyggda funktioner för elektronisk signatur. Du kan även skapa anpassade signaturkrav för alla databastabeller och fält.

- [Elektroniska underskrifter – översikt](electronic-signature-overview.md)
- [Ställa in elektroniska signaturer](tasks/set-up-electronic-signatures.md) (Uppgiftsguide)

## <a name="case-management"></a>Ärendehantering

Genom att planera, spåra och analysera ärenden kan du utveckla effektiva lösningar som kan användas för liknande ärenden. När exempelvis kundtjänstmedarbetare eller allmänkunniga inom personalavdelningen skapar ärenden, kan de hitta information i kunskapsbasartiklar som hjälper dem att arbeta med eller slutföra ett ärende mer effektivt.

- [Översikt över ärendehantering](cases.md)
- [Planera kategorisäkerhet, ärendeprocesser och kategorier för ärenden](plan-case-management.md)

## <a name="record-templates"></a>Postmallar

Bokföringsmallar hjälper dig att skapa poster snabbare. Du kan skapa en bokföringsmall så att fältvärden som ofta används inte måste anges explicit för varje enskild ny post.

- [Postmallar – översikt](record-templates.md)
- [Skapa en bokföringsmall som underlättar datainmatning](../../dev-itpro/data-entities/tasks/create-record-template-facilitate-data-entry.md) (uppgiftsguide)
- [Använd en bokföringsmall för att skapa en ny post](../../dev-itpro/data-entities/tasks/use-record-template-new-record.md) (uppgiftsguide)

## <a name="general-organization-administration"></a>Allmän organisationsadministration

- [Ändra banner eller logotypen](../get-started/tasks/change-banner-or-logo.md) (Uppgiftsguide)
- [Konfigurera dokumenthantering](configure-document-management.md)
- [Konfigurera och skicka e-post](configure-email.md)
- [Datum/tidsdata och tidszoner](date-time-zones.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]