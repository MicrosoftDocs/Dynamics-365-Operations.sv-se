---
title: Kopiera leverantörer genom att använda delade nummerserier
description: Det här avsnittet beskriver hur du använder delade nummerserier för att kopiera en leverantör till en annan juridisk person men behålla samma leverantörs-ID.
author: mikefalkner
manager: aolson
ms.date: 08/24/2018
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 320487c451dd63ca861a13fc490e60d561486e0b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4979223"
---
# <a name="copy-vendors-by-using-shared-number-sequences"></a>Kopiera leverantörer genom att använda delade nummerserier

[!include [banner](../includes/banner.md)]

Du kan använda delade nummerserier för att tilldela leverantörs-ID. Med delade nummerserier kan du också kopiera leverantörer från en juridisk person till annan juridisk person men använda samma leverantörs-ID för båda.

## <a name="setup"></a>Konfigurera

Funktionen aktiveras när du använder en delad nummerserie för att tilldela leverantörs-ID. Du måste använda samma nummerserie för varje juridisk person som du vill kopiera leverantören till. Du ändrar leverantörens nummerserie på sidan **parametrar för leverantörsreskontra** för varje juridisk person. Välj **Leverantörsreskontra** \> **Inställningar** \> **Parametrar för leverantörsreskontra** och välj sedan fliken **Nummerserier**.

Du kan också ställa in leverantörsnummerserier för varje leverantörsgrupp. Dessa nummerserier måste också delas. Nummerserien för en leverantörsgrupp används först. Om ingen nummerserie angivits för en leverantörsgrupp används den nummerserie som har angetts på sidan **Parametrar för leverantörsreskontra**.

Om du använder manuella leverantörs-ID kan du också kopiera leverantörer mellan juridiska personer. Men om du försöker kopiera en leverantör till en juridisk person där leverantörs-ID redan finns startas inte kopieringen.

## <a name="copy-a-vendor"></a>Kopiera en leverantör

För att kopiera en leverantör väljer du **Ny** på listsidan **Alla leverantörer** för att öppna sidan **Alla leverantörer, ny post**. Observera att tilldelningen av ett nytt leverantörs-ID inte sker direkt. Det här skiljer sig från hur det har fungerat i tidigare versioner. Eftersom du inte har markerat leverantörsgruppen ännu kan systemet inte avgöra vilken nummerserie som ska användas. Dessutom kan systemet inte avgöra om du vill skapa en ny leverantör eller kopiera en leverantör. Därför tilldelas inte leverantörs-ID förrän du väljer **Spara** längst ned på sidan.

Om du skapar en ny leverantör kan du fortsätta att fylla i alla fält precis som vanligt. När du är klar och väljer **Spara** tilldelas leverantörs-ID automatiskt. För manuella nummerserier kan du se att ditt manuella leverantörs-ID har använts.

För att kopiera en leverantör fyller du i en eller flera bokstäver i det leverantörsnamn du söker i fältet **Namn**. En dialogruta visar en lista över parter som kanske är den leverantör du söker. Ytterligare information visas till höger i dialogrutan när du väljer en av parterna:

- Fliken **Allmänt** visar telefonnummer och adress.
- Fliken **Roller** visar de roller som den valda parten kan ha och i vilken juridisk person den har varje roll.
- Fliken **Momsregistrerings-ID** visar de momsregistrerings-ID som har tilldelats parten.

Du kan kopiera en part endast om parten har en leverantörsroll och har den rollen i en juridisk person som inte är den aktuella juridiska personen. Följ dessa steg när du har hittat en part som uppfyller dessa villkor.

1. Alternativet **Kopiera leverantör** visas. Standardvärdet för det här alternativet är **Nej**. Om du vill kopiera leverantören till den aktuella juridiska personen väljer du alternativet **Ja**. 
2. Fältet **juridisk person** visas. Välj den juridiska person du vill kopiera leverantören från. Om leverantören finns endast i en juridisk person ställs fältet automatiskt in till den juridiska personen.
3. Välj **Välj**. Den nya leverantören skapas.

## <a name="validation"></a>Validering

När du kopierar en leverantör försöker systemet spara den nya leverantörsinformationen. Valideringar körs för att säkerställa att kopierade data är rätt. Du får ett felmeddelande för varje verifiering som misslyckas. Felmeddelandena förklarar vilken information som måste uppdateras. Det går inte att spara kopian av leverantören förrän du har åtgärdat alla valideringsfel.

## <a name="copy-a-vendor-by-using-the-tax-exempt-number-search-feature"></a>Kopiera en leverantör genom att använda sökfunktionen för momsregistereringsnummer

Du kan även kopiera leverantörer med hjälp av sökfunktionen för momsregistreringsnummer i gruppen **Registrering** i fliken **Leverantör** i åtgärdsfönstret på sidan **Alla leverantörer**. Dialogrutan **Sök momsregistreringsnummer** visar momsregistreringsnummer, leverantörs-ID, leverantörens namn och den juridiska person där momsregistreringsnumret används. Du kan kopiera en leverantör om den finns i en juridisk person som inte är den aktuella juridiska personen. Gör följande när du väljer en leverantör som uppfyller detta kriterium.

1. Alternativet **Kopiera leverantör** visas. Standardvärdet för det här alternativet är **Nej**. Om du vill kopiera leverantören till den aktuella juridiska personen väljer du alternativet **Ja**.
2. Välj **Välj**. Den nya leverantören skapas.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]