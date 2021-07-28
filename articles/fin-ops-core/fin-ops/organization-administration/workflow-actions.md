---
title: Åtgärder i godkännandeprocesser i ett arbetsflöde
description: Det här avsnittet innehåller en beskrivning av åtgärder som alla deltagare i en arbetsflödesgodkännandeprocess kan utföra.
author: ChrisGarty
ms.date: 08/23/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 56411
ms.assetid: 65fb711c-6474-42d1-81ed-ca657c29bf1f
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2da54d147c7e9c8a42ef9de94abcbe7f36c98295
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/06/2021
ms.locfileid: "6355758"
---
# <a name="actions-in-workflow-approval-processes"></a>Åtgärder i godkännandeprocesser i ett arbetsflöde

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller en beskrivning av åtgärder som alla deltagare i en arbetsflödesgodkännandeprocess kan utföra.

Ett arbetsflöde kan omfatta flera grupper med personer: upphovsmannen, de som tilldelats uppgifter, beslutsfattare och godkännare. I följande arbetsflöde för utgiftsrapporter är Sam upphovsmannen, medlemmarna i kön har tilldelats uppgifter, John är beslutsfattare och Frank, Sue och Ann är godkännare.

[![Arbetsflöde\_MedManuelltBeslut.](./media/workflow_withmanualdecision.gif)](./media/workflow_withmanualdecision.gif)

Följande avsnitt förklarar de arbetsflödesåtgärder som respektive grupp kan utföra.

## <a name="actions-that-an-originator-can-perform"></a>Åtgärder som en upphovsman kan utföra

Upphovsmannen startar en arbetsflödesinstans genom att skicka ett dokument för bearbetning. Till exempel måste Sam klicka på **Skicka** på sidan **Utgiftsrapport** för att skicka in sin utgiftsrapport.

## <a name="actions-that-a-task-assignee-can-perform"></a>Åtgärder som någon som tilldelats en uppgift kan utföra

En uppgift kan tilldelas flera kontakter eller en arbetsuppgiftskö som övervakas av flera personer. Det är dock endast en person som kan genomföra en uppgift. Till exempel har Sam skickat en utgiftsrapport och lämnat sina kvitton till organisationens utgiftsrapportavdelning för granskning.

Medlemmarna i utgiftsrapportavdelningen på Adventure Works övervakar kön. Julie, en medlem på avdelningen, har accepterat uppgiften för granskning av Sams utgiftsrapport och kvitton. Hon kan nu utföra någon av följande åtgärder: slutföra, avvisa, delegera, begära ändring, omtilldela eller frisläppa.

> [!NOTE]
> Vilka åtgärder som står till buds varierar beroende på hur uppgiften har utformats av programutvecklaren.

### <a name="complete"></a>Slutföra

När en användare slutför en uppgift tilldelas dokumentet som skickades för bearbetning till nästa användare i arbetsflödet om det finns en nästa användare. Om ingen ytterligare bearbetning krävs avslutas arbetsflödesprocessen.

Till exempel har Julie, som arbetar på utgiftsrapportavdelningen på Adventure Works, accepterat uppgiften att granska Sams utgiftsrapport och kvitton. När Julie slutför sin granskning tilldelas dokumentet till John.

### <a name="reject"></a>Avvisa

När en användare avvisar ett dokument avslutas arbetsflödesprocessen.

Till exempel har Julie, som arbetar på utgiftsrapportavdelningen på Adventure Works, accepterat uppgiften att granska Sams utgiftsrapport och kvitton. Om Julie avvisar utgiftsrapporten avslutas arbetsflödesprocessen.

Sedan kan Sam skicka utgiftsrapporten på nytt. Han kan göra ändringar först eller skicka om den ursprungliga versionen. Om Sam skickar om utgiftsrapporen startar arbetsflödesprocessen vid uppgiften för manuell granskning.

### <a name="delegate"></a>Delegera

När en användare delegerar en uppgift tilldelas den en annan användare.

Till exempel har Julie, som arbetar på utgiftsrapportavdelningen på Adventure Works, accepterat uppgiften att granska Sams utgiftsrapport och kvitton. Julie delegerar den här uppgiften till Tim, som är hennes medhjälpare.

Tim agerar sedan på uppdrag av Julie. Därför, när Tim slutar sin granskning, tilldelas utgiftsrapporten till John, som om Julie hade slutfört uppgiften.

### <a name="request-change"></a>Begär ändring

När en användare begär en ändring av ett dokument som har skickats, skickas dokumentet tillbaka till upphovsmannen.

Till exempel har Julie, som arbetar på utgiftsrapportavdelningen på Adventure Works, accepterat uppgiften att granska Sams utgiftsrapport och kvitton. Julie upptäcker några fel i utgiftsrapporten och begär ändringar. Utgiftsrapporten skickas tillbaka till Sam.

Sam kan skicka utgiftsrapporten på nytt. Han kan göra nödvändiga ändringar först eller skicka om den ursprungliga versionen. Om Sam skickar om utgiftsrapporten måste en medlem i arbetsuppgiftskön granska utgiftsrapporten och kvittona igen.

### <a name="reassign"></a>Tilldela om

Medlemmarna i en arbetsuppgiftskö kan tilldela om dokument som finns i kön till en annan kö.

Exempelvis övervakar Julie, som arbetar på utgiftsrapportsavdelningen på Adventure Works, kön. För att balansera arbetsbelastningen kan hon tilldela om utgiftsrapporten och de kvitton som ingår i den till en annan kö.

### <a name="release"></a>Frisläpp

Ibland kan en medlem av en arbetsuppgiftskö acceptera en uppgift, men sedan bestämma sig för att inte genomföra uppgiften. I det här fallet kan personen som accepterade uppgiften frisläppa dokumentet tillbaka till arbetsuppgiftskön.

Till exempel har Julie, som arbetar på utgiftsrapportavdelningen på Adventure Works, accepterat uppgiften att granska Sams utgiftsrapport och kvitton. Om Julie väljer att hon inte kan genomföra uppgiften, kan hon frisläppa dokumentet. Utgiftsrapporten returneras till kön, så att andra medlemmar på utgiftsrapportsavdelningen på Adventure Works kan slutföra uppgiften.

## <a name="actions-that-a-decision-maker-can-perform"></a>Åtgärder som en beslutsfattare kan utföra

Vanligtvis tilldelas ett dokument till en beslutsfattare eftersom det finns en fråga som beslutsfattaren måste besvara. Svaret på frågan är oftast **Ja** eller **Nej** eller **Sant** eller **Falskt**. Om beslutsfattaren inte väljer något av dessa alternativ kan han eller hon delegera beslutet.

### <a name="choice-1-or-choice-2"></a>\[Alternativ 1\] eller \[Alternativ 2\]

En beslutsfattare måste besvara en fråga som är relaterad till dokumentet. Svaret på frågan är oftast **Ja** eller **Nej** eller **Sant** eller **Falskt**. Svaret som beslutsfattaren väljer avgör arbetsflödesförgreningen som används för att bearbeta dokumentet.

Till exempel tilldelas Sams utgiftsrapport till John. John måste bestämma om informationen i dokumentet kräver ett samtal till Sams chef. Om John beslutar att ett samtal krävs tilldelas utgiftsrapporten till Aretha, som sedan måste ringa Sams chef. Om John anser att ett samtal inte krävs tilldelas utgiftsrapporten till Frank för godkännande.

### <a name="delegate"></a>Delegera

När en beslutsfattare delegerar ett beslut tilldelas dokumentet till en annan användare som måste fatta beslutet.

Till exempel tilldelas Sams utgiftsrapport till John. John delegerar beslutet till Maria, som är hans assistent.

Maria agerar sedan på uppdrag av John. Om Maria beslutar att ett samtal till Sams chef krävs tilldelas utgiftsrapporten till Aretha, som måste ringa Sams chef. Om Maria anser att ett samtal inte krävs tilldelas utgiftsrapporten till Frank för godkännande.

## <a name="actions-that-an-approver-can-perform"></a>Åtgärder som en godkännare kan utföra

När ett dokument tilldelas en godkännare, kan denne vidta någon av följande åtgärder: godkänna, avvisa, delegera eller begära ändringar.

### <a name="approve"></a>Godkänna

När en godkännare godkänner ett dokument, tilldelas det nästa användare i arbetsflödet, om det finns en nästa användare. Om ingen ytterligare bearbetning krävs avslutas arbetsflödesprocessen.

Till exempel har Sam skickat en utgiftsrapport på 6 000 USD och detta dokument har tilldelats till Frank. Om Frank godkänner dokumentet skickas det vidare till Sue för godkännande. När Sue har godkänt utgiftsrapporten avslutas arbetsflödesprocessen.

### <a name="reject"></a>Avvisa

När en godkännare avvisar ett dokument, avslutas bearbetningen av arbetsflödet.

Till exempel har Sam skickat en utgiftsrapport på 12 000 USD och detta dokument har tilldelats till Sue. Om Sue avslår utgiftsrapporten avslutas arbetsflödesprocessen.

Sam kan skicka utgiftsrapporten på nytt. Han kan göra nödvändiga ändringar först eller skicka om den ursprungliga versionen av utgiftsrapporten. Om Sam skickar om utgiftsrapporten startar arbetsflödesprocessen vid godkännandeprocessen.

### <a name="delegate"></a>Delegera

När en godkännare delegerar ett dokument, tilldelas dokumentet en annan användare för godkännande.

Till exempel har Sam skickat en utgiftsrapport på 12 000 USD och detta dokument har tilldelats till Frank. Frank delegerar utgiftsrapporten till Ann.

Ann agerar då i Franks ställe. Om Ann godkänner dokumentet tilldelas det till Sue för godkännande, precis som om Frank hade godkänt det. Så snart Sue har godkänt dokumentet skickas det vidare till Ann för godkännande.

### <a name="request-change"></a>Begär ändring

När en godkännare begär en ändring av ett dokument, skickas det tillbaka till upphovsmannen.

Till exempel har Sam skickat en utgiftsrapport på 12 000 USD och detta dokument har tilldelats till Sue. Om Sue begär ändringar skickas utgiftsrapporten tillbaka till Sam.

Sam kan skicka utgiftsrapporten på nytt. Han kan göra nödvändiga ändringar först eller skicka om den ursprungliga versionen av utgiftsrapporten. Om Sam skickar om utgiftsrapporten skickas den till Frank för godkännande eftersom Frank är den första godkännaren i godkännandeprocessen.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]