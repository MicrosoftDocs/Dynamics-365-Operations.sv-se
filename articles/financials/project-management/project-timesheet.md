---
title: Mobilappen Project Timesheet
description: Det här avsnittet innehåller information om mobilappen Microsoft Dynamics 365 Project Timesheet. Mobilappen Project Timesheet låter användare skicka och godkänna tidrapporter för projekt på sin mobila enhet.
author: abruer
manager: AnnBe
ms.date: 04/08/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: josaw1
ms.dyn365.ops.version: 10
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: a475085001b8fa10814c864ef35129eb6ebfdfef
ms.sourcegitcommit: 9796d022a8abf5c07abcdee6852ee34f06d2eb57
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/12/2019
ms.locfileid: "969701"
---
# <a name="microsoft-dynamics-365-project-timesheet-mobile-application"></a>Microsoft Dynamics 365 Project Timesheet mobilapp

[!include [banner](../includes/banner.md)]

## <a name="overview"></a>Översikt

Mobilappen Microsoft Dynamics 365 Project Timesheet låter användare skicka och godkänna tidrapporter för projekt på sin mobila enhet (iPhone eller Android). Denna mobilapp visar tidrapportfunktionerna som finns i projekthanterings- och redovisningsområdet i Microsoft Dynamics 365 for Finance and Operations förbättra användarproduktivitet och effektivitet samt möjliggöra snabb registrering och godkännande av projekttidrapporter.

## <a name="download-and-install-the-mobile-app"></a>Hämta och installera mobilappen

Hämta och installera Microsoft Dynamics 365 Project Timesheet mobilapp för Android eller iPhone från mobila butiken för enheten.

## <a name="enable-the-app"></a>Aktivera appen 

I Dynamics 365 for Finance and Operations måste mobilappen Project Timesheet aktiveras. Aktivera funktionen genom att gå till **projekthanterings- och redovisningsparametrar \> tidrapport** och välj parametern **aktivera Microsoft Dynamics 365 Project Timesheet**.

## <a name="sign-in-to-the-app"></a>Logga in på appen

1.  Starta appen i din mobila enhet.

2.  Ange din Microsoft Dynamics 365 for Finance and Operations URL.

3.  Första gången du loggar in uppmanas du ange användarnamn och lösenord. Ange dina autentiseringsuppgifter.

4.  Du kommer att vara inloggad på standardföretaget.

## <a name="submit-a-project-timesheet"></a>Skicka en projekttidrapport

Du kan skapa och skicka en projekttidrapport i appen. Du kan basera en ny tidrapport på information från en tidigare tidrapport, sparade rader eller projekttilldelningar. Om du är angivna som ett ombud, kan du även ange en tidrapport för en annan anställd. Om du vill skapa en tidrapport som ombud väljer du knappen **meny** och väljer ett resursnamn.

Tidrapportsidan skapar en ny tidrapport för tidrapportperioden baserat på det aktuella datumet. Arbetsveckan visas. Om tidrapportperioden omfattar flera veckor, kan du välja en annan arbetsvecka från flikarna med arbetsvecka.
Om det finns en tidrapport för det aktuella datumet visas den. Om du behöver skapa en ny tidrapport i en annan tidrapportperiod väljer du knappen **meny** och väljer sedan **ny tidrapport**.

Du kan ange information om projekt genom att klicka på åtgärden **lägg till tid** eller **kopiera tid från**. Åtgärden **kopiera tid från** kopierar projektinformation för raden, men inte timmar. **Kopiera tid från**-menyn innehåller följande alternativ.

- **Kopiera från den befintlig tidrapporten** - kopiera tidrapportrader från en befintlig tidrapport.

- **Kopiera från favorit** - Skapa nya tidrapportrader, med hjälp av tidrapportinställningarna du valde som favoriter.

- **Kopiera från tilldelning** - skapa nya tidrapportrader från tilldelade projekt.

Projektinformationen som visas beror på de mobila parametrar som du har definierat på sidan **projekthanterings- och redovisningsparametrar**.

I fältet **Juridisk person** väljer du den juridiska person som du utförde projektarbetet för. Fältet **Juridisk person** är endast tillgängligt om koncernintern tidrapportsupport har aktiverats för din juridiska person.

Välj den kund som är kopplad till projektet för tidrapporten. För den ursprungliga versionen på Android stöds inte transaktion per kund eftersom du först måste välja projektet. Om du har valt projektet först fylls fältet **kund** i automatiskt.

I fältet **Projekt** väljer du det projekt som du angav tid för. Fältet **Kund** fylls automatiskt.

Kund- och projektsökningarna låter dig söka i både kunder och projekt.

Markera informationen i fälten **kategori**, **aktivitet**, **radegenskap**, **momsgrupp** och **artikelmomsgrupp** efter behov. Dessa fält kan åsidosättas.

Fältet **radegenskap** anges till ett standardvärde baserat på projekthanterings- och redovisningsparametrar. När parametrarna projekt/kategori och kategori/resurs aktiveras kommer värdet **radegenskap** att anges till det standardvärde som har definierats för verifieringen. När parametrarna projekt/kategori och kategori/resurs inte är aktiverade är värdet **radegenskap** standard enligt fältet **aktivera standardradegenskap** på sidan **projekthanterings- och redovisningsparametrar**. Värdet **Radegenskap** kan åsidosättas.

Välj en dag för att lägga till tid. Ange antalet timmar som du har arbetat varje dag.

Lägg till kommentarer om timmarna som du anger genom att klicka på **Lägg till kommentarer** och ange kommentarer för en intern målgrupp, kundmålgrupp eller båda.
Interna kommentarer kan visas av projekthanterarna. Kundkommentarer inkluderas på fakturor.

Markera kryssrutan och klicka sedan på **Spara som favorit** om du vill spara raden som en favorit.

Stöd för ekonomisk dimension och bilaga ges inte i mobilappen.

Fortsätt lägga till projektrader som behövs för att slutföra din tidrapport.

Klicka på **Skicka** om du vill skicka tidrapporten till godkännandearbetsflödet.

## <a name="review-timesheets"></a>Granska tidrapporter

En lista över tidrapporter som behöver granskas är tillgänglig på menyn. Det här alternativet är bara tillgängligt om du har blivit utsedd till en arbetsflödesgodkännare. Både rubriken och godkännande av rader stöds. Godkännande på radnivå ger dig möjlighet att markera en eller flera rader för godkännande. När du har granskat tidrapportinformationen klickar du på **Godkänn**, **Delegera**, eller **Returnera** för att fortsätta arbetsflödet.
