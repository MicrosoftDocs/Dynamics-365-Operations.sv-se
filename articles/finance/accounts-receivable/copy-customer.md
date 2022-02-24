---
title: Kopiera kunder genom att använda delade nummerserier
description: Det här avsnittet beskriver hur du använder delade nummerserier för att kopiera en kund till en annan juridisk person men behålla samma kund-ID.
author: mikefalkner
manager: aolson
ms.date: 08/31/2018
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 91f7568ea8364f97de7e514fb207191ee00041a5
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4459918"
---
# <a name="copy-customers-by-using-shared-number-sequences"></a>Kopiera kunder genom att använda delade nummerserier

[!include [banner](../includes/banner.md)]

Du kan använda delade nummerserier för att tilldela kund-ID. Med delade nummerserier kan du också kopiera kunder från en juridisk person till annan juridisk person men använda samma kund-ID för båda.

## <a name="setup"></a>Konfigurera

Funktionen aktiveras när du använder en delad nummerserie för att tilldela kund-ID. Du måste använda samma nummerserie för varje juridisk person som du vill kopiera kunden till. Du ändrar kundens nummerserie på sidan **parametrar för kundreskontra** för varje juridisk person. Välj **Kundreskontra** \> **Parametrar** och sedan fliken **Nummerserier**.

Du kan också ställa in kundnummerserier för varje kundgrupp. Dessa nummerserier måste också delas. Nummerserien för en kundgrupp används först. Om ingen nummerserie angivits för en kundgrupp används den nummerserie som har angetts på sidan **Parametrar för kundreskontra**.

Om du använder manuella kund-ID kan du också kopiera kunder mellan juridiska personer. Men om du försöker kopiera en kund till en juridisk person där kund-ID redan finns startas inte kopieringen.

## <a name="copy-a-customer"></a>Kopiera en kund

För att kopiera en kund väljer du **Ny** på listsidan **Alla kunder** och öppnar dialogrutan **Skapa kund**. Observera att tilldelningen av ett nytt kund-ID inte sker direkt. Det här skiljer sig från hur det har fungerat i tidigare versioner. Eftersom du inte har markerat kundgruppen ännu kan systemet inte avgöra vilken nummerserie som ska användas. Dessutom kan systemet inte avgöra om du vill skapa en ny kund eller kopiera en kund. Därför tilldelas inte kund-ID förrän du väljer **Spara** längst ned i dialogrutan.

Om du skapar en ny kund kan du fortsätta att fylla i alla fält precis som vanligt. När du är klar och väljer **Spara** tilldelas kund-ID automatiskt. För manuella nummerserier kan du se att ditt manuella kund-ID har använts.

För att kopiera en kund fyller du i en eller flera bokstäver i det kundnamn du söker i fältet **namn**. En dialogruta visar en lista över parter som kanske är den kund du söker. Ytterligare information visas till höger i dialogrutan när du väljer en av parterna:

- Fliken **Allmänt** visar telefonnummer och adress.
- Fliken **Roller** visar de roller som den valda parten kan ha och i vilken juridisk person den har varje roll.
- Fliken **Momsregistrerings-ID** visar de momsregistrerings-ID som har tilldelats parten.

Du kan kopiera en part endast om parten har en kundroll och har den rollen i en juridisk person som inte är den aktuella juridiska personen. Följ dessa steg när du har hittat en part som uppfyller dessa villkor.

1. Alternativet **Kopiera kund** visas. Standardvärdet för det här alternativet är **Nej**. Om du vill kopiera kunden till den aktuella juridiska personen väljer du alternativet **Ja**. 
2. Fältet **juridisk person** visas. Välj den juridiska person du vill kopiera kunden från. Om kunden finns endast i en juridisk person ställs fältet automatiskt in till den juridiska personen.
3. Välj **Välj**. Den nya kunden skapas.

## <a name="validation"></a>Validering

När du kopierar en kund försöker systemet spara den nya kundinformationen. Valideringar körs för att säkerställa att kopierade data är rätt. Du får ett felmeddelande för varje verifiering som misslyckas. Felmeddelandena förklarar vilken information som måste uppdateras. Det går inte att spara kopian av kunden förrän du har åtgärdat alla valideringsfel.

## <a name="copy-a-customer-by-using-tax-exempt-number-search-feature"></a>Kopiera en kund genom att använda sökfunktionen för momsregistreringsnummer

Du kan även kopiera kunder med hjälp av sökfunktionen för momsregistreringsnummer i gruppen **Registrering** på fliken **Kund** i åtgärdsfönstret på sidan **Alla kunder**. Dialogrutan **Sök momsregistreringsnummer** visar momsregistreringsnummer, kund-ID, kundens namn och den juridiska person där momsregistreringsnumret används. Du kan kopiera en kund om den finns i en juridisk person som inte är den aktuella juridiska personen. Gör följande när du väljer en kund som uppfyller detta kriterium.

1. Alternativet **Kopiera kund** visas. Standardvärdet för det här alternativet är **Nej**. Om du vill kopiera kunden till den aktuella juridiska personen väljer du alternativet **Ja**. 
2. Välj **Välj**. Den nya kunden skapas.
