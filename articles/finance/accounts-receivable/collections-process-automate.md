---
title: Automatisering av inkassoprocess
description: I den här artikeln beskrivs hur du ställer in processtrategier för inkasso som automatiskt identifierar kundfakturor som kräver en e-postpåminnelse, inkassoaktivitet eller ett kravbrev som ska skickas till kunden.
author: JodiChristiansen
ms.date: 03/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustomerCollectionManagerWorkspace
audience: Application User, IT Pro
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-08-26
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 9ec749db197b4d04ee2e99ac7a16f4f2120c6707
ms.sourcegitcommit: 427fe14824a9d937661ae21b9e9574be2bc9360b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/09/2022
ms.locfileid: "8946191"
---
# <a name="collections-process-automation"></a>Automatisering av inkassoprocess

[!include [banner](../includes/banner.md)]

I den här artikeln beskrivs hur du ställer in processtrategier för inkasso som automatiskt identifierar kundfakturor som kräver en e-postpåminnelse, inkassoaktivitet (t.ex. ett telefonsamtal) eller ett kravbrev som ska skickas till kunden. 

Organisationer ägnar en lång tid på att undersöka föråldrade saldorapporter, kundkonton och öppna fakturor för att lära dig vilka kunder som måste kontaktas om en öppen faktura eller ett kontosaldo. Den här forskningen tar tid från en inkassohandläggare som används för att kommunicera med kunder för att samla in förfallna saldon eller lösa tvister om fakturan. Med automatisering av inkassoprocesser kan du ställa in ett strategibaserade tillvägagångssätt för din insamlingsprocess. På så sätt kan du utföra inkassoaktiviteter på ett konsekvent sätt genom att tillhandahålla anpassade e-postpåminnelser eller en programmerad process för sändning av kravbrev. 

## <a name="collections-process-setup"></a>Inställningar för insamlingsprocess
På sidan **Inställningar för insamlingsprocess** (**Kredit och inkasso > Inställningar > Inställningar för insamlingsprocess**) för att skapa en automatiserad inkassoprocess som schemalägger aktiviteter, skickar e-postmeddelanden och skapar och bokför kundkravbrev. Processtegen baseras på den första eller äldsta öppna fakturan. I varje steg används den här fakturan för att fastställa vilken kommunikation eller aktivitet som ska utföras med en viss kund.  

Inkassoteam skickar vanligtvis ut ett tidigt meddelande om varje utestående faktura så att en kund meddelas när fakturan är på väg att förfalla. Valet för **förkrav** kan ställas in så att ett steg i varje processhierarki kan användas på varje faktura när fakturatidsinställningen når detta steg.

### <a name="process-hierarchy"></a>Processhierarki
Varje kundpool kan bara tilldelas en processmall. Rankningen av hierarkin för det här steget identifierar vilken process som ska prioriteras om en kund ingår i fler än en pool som har tilldelats en processmall. Pool-ID bestämmer vilka kunder som ska tilldelas processen. Varje hierarki som konfigureras kan bara tilldelas en processautomatisering.

Tysta dagar används för att säkerställa att kunden inte kontaktas för ofta via den automatiska processen. Om t.ex. tysta dagar är inställt på två kontaktas inte en kund av den automatiserade processen under minst två dagar, även om den ursprungliga inköpsfakturan har kvittats helt. 

Om du vill utesluta kunder från processautomatiseringen om kundens åldersbalans eller fakturabelopp är mindre än ett definierat värde väljer du **Åldersfördelade kunder mindre än** eller **Fakturabelopp mindre än** i fältet **Exkludera från process** och ange beloppets värde.

Markera **Använd förutsägelser** för att skapa insamlingsaktiviteter med hjälp av kundbetalningsprognoser. Aktiviteterna som skapas använder aktivitetsmallen från **Betalningsprognoser** på sidan **Parametrar för kundreskontra**, fliken, **Automatisering av inkassoprocess**. 

### <a name="process-details"></a>Processdetaljer
Klicka på **Ny** om du vill lägga till en ny processinformation i hierarkin. **Beskrivning** används för att identifiera syfte eller namn på steget i hierarkin. Välj **Åtgärdstyp** för att definiera steget som ska skapa en aktivitet, skicka ett e-postmeddelande eller skapa ett kravbrev. 

- **Affärsdokument** definieras den mall som används för att skapa åtgärdstypen. Detta dokument kan vara en aktivitetsmall, en e-postmall eller ett kravbrev som skickas till varje kund. Med inkassoprocessautomatisering skapas kravbrev per kund, oavsett hur andra inkassoparametrar är inställda.
- **När** definierar processteget som kommer att inträffa före eller efter det ledande (äldsta) förfallodatumet för fakturan och används tillsammans med det nummer som visas i **Dagar i relation till kolumnen fakturaförfallodatum**.  
- Markera alternativet **förkrav** om du vill skapa en åtgärd för varje faktura i ett steg i en processhierarki. Åtgärden förkrav är vanligtvis ut ett tidigt meddelande om utestående fakturor så att en kund meddelas när fakturan är på väg att förfalla. Förkrav kan bara markeras för en aktivitet per hierarki. När du väljer en e-poståtgärdstyp, används mottagaren för att definiera om e-postmeddelandet ska skickas till en kund, säljgrupp eller inkassohandläggare. 
- Värdet i fältet **kontakt för arbetssyfte** kommer sedan avgöra vilken kontakt från kundkontot som ska ta emot kommunikationen.

### <a name="business-document-details"></a>Detaljer för affärsdokument
Detaljer för affärsdokument varierar beroende på vilken åtgärdstyp som har valts i processdetaljerna. När åtgärdstypen är en aktivitet visas aktivitetsmallen information. Informationen omfattar mallnamnet, den typ av aktivitet som skapas, syftet med aktiviteten, antalet schemalagda dagar som aktiviteten ska slutföras till och information om aktiviteten. Denna aktivitet kommer sedan att länka till den inledande fakturan som talar om för mottagaren om vilken åtgärd som krävs för att slutföra aktiviteten.

Om åtgärdstypen är ett e-postmeddelande i processdetaljerna kommer det här avsnittet att innehålla två snabbflikar. Den första används för att definiera mall-ID, e-postbeskrivning, standardspråk, användarnamnet som tilldelas e-postmeddelanden som skickas automatiskt och den associerade e-postadressen för avsändare. Det andra innebär att brödtexten i e-postmeddelandet skapas efter att värdena i fälten **språk** och **ämne** har sparats genom att välja **Redigera**. Då öppnas ett fönster där HTML-innehållet kan överföras. 

> [!Note]
> Du kan spara ett e-postmeddelande i Outlook som innehåller brödtexten i kommunikationen i HTML-format. Du kan sedan överföra meddelandeinnehållet för att implementera mallen. <br> <br> Om åtgärdstypen för kravbrev väljs, visas inte avsnittet affärsdokument information på sidan inställningar.

Använd knappen **Historik för inkassoprocess** om du vill visa den senaste historiken för den valda processhierarkin. 

Klicka på åtgärden **Insamlingsprocessuppgift** om du vill visa kunder som har tilldelats en inkassoprocess. Använd **Förhandsgranskning av kundtilldelning** när du vill visa hierarkin som en viss kund har tilldelats. Använd **Förhandsgranskning av processtilldelning** när du vill förhandsgranska kunderna som tilldelas en hierarki när de körs. Klicka på **Manuell tilldelning** för att visa kunder som har tilldelats en process manuellt eller välj vilka kunder som ska tilldelas en process.

Klicka på åtgärden **Processsimulering** för att förhandsgranska de åtgärder som kommer att skapas om den valda processautomatiseringen körs just nu. 

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
