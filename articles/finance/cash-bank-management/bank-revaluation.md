---
title: Bank – omräkning i utländsk valuta
description: Det här avsnittet innehåller en översikt över processen för bank – omräkning i utländsk valuta. Den innehåller information om inställningar, köra processen, beräkningen för processen och återföring av ombedömningstransaktioner.
author: roschlom
ms.date: 05/16/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankCurrencyRevalHistory
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2019-03-08
ms.dyn365.ops.version: 10
ms.openlocfilehash: 3df6a22e06abbfa75a12ffddac242dd34f5beba5
ms.sourcegitcommit: 408786b164b44bee4e16ae7c3d956034d54c3f80
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/05/2021
ms.locfileid: "7754130"
---
# <a name="bank-foreign-currency-revaluation"></a>Bank – omräkning i utländsk valuta

[!include [banner](../includes/banner.md)]


Det här avsnittet innehåller en översikt över processen för bank – omräkning i utländsk valuta. Den förklarar hur du ställer in och kör processen och ger information om beräkningar för processen. Den förklarar också hur du återför ombedömningstransaktionen om återföring krävs.

Som en del av ett periodslut kräver redovisningspraxis att bankkontosaldon i utländska valutor omvärderas med hjälp av olika valutakurstyper (aktuella, tidigare, genomsnittliga osv.). Funktionen för bank – omräkning i utländsk valuta kan användas för att omräkna en eller flera bankkonton. Den här funktionen är även en global funktion. Därför kan du från en enda sida omvärdera banker över de juridiska personer som du har tillgång till.

> [!NOTE]
> När du kör ombedömningsprocessen kommer saldot i varje bankkonto som bokförs i utländsk valuta att omvärderas. Orealiserade vinst- eller förlusttransaktioner som skapas under ombedömningsprocessen genereras av systemet. Två transaktioner kan komma att skapas, en för redovisningsvalutan och en för rapporteringsvalutan om en rapporteringsvaluta är relevant. Varje redovisningspost bokförs till orealiserad vinst eller förlust samt det huvudkonto som omvärderas.

## <a name="prepare-to-run-foreign-currency-revaluation"></a>Förbereda en körning av omvärdering i utländsk valuta

Innan du kan köra ombedömningsprocessen måste följande inställningar göras.

- Ange valutakurstypen åpå sidan **Redovisning**. Om en valutakurstyp inte är definierad på huvudkontot, används denna valutakurstyp i samband med omräkning i utländsk valuta.
- Ange realiserad vinst, realiserad förlust, orealiserad vinst och orealiserad förlust för valutaomvärdering på sidan **Redovisning**. Realiserad vinstkonton och realiserad förlustkonton används när kundreskontra- och leverantörsreskontratransaktioner kvittas. Orealiserad vinstkonton och orealiserad förlustkonton används för att omvärdera öppna transaktioner och huvudkonton för redovisning.
- På sidan **Valutaombedömningskonton** kan du välja olika valutaombedömningskonton för varje valuta och företag. Om inga konton har definierats används kontona från sidan **Redovisning**.

## <a name="enable-foreign-currency-revaluation"></a>Aktivera omvärdering i utländsk valuta

Du måste aktivera funktionen för bank – omvärdering i utländsk valuta innan du kan bearbeta omvärdering i utländsk valuta.

1. Gå till **Kassa- och bankhantering \> Inställningar \> Parametrar för kassa- och bankhantering**.
2. På fliken **Allmänt** under **omvärdering i utländsk valuta** anger du alternativet **aktivera bankomvärdering** till **Ja** för att aktivera funktionen för den aktuella juridiska personen. 
3. På fliken **nummerserier** lägger du till en nummerserie för omvärdering i utländsk valuta.
4. Uppdatera webbläsaren för att se **omvärdering i utländsk valuta** i avsnittet **periodiska uppgifter** på områdessidan.

Du måste aktivera funktionen för varje juridisk person som används för omvärdering i utländsk valuta. Om du har tilldelats rollen som systemadministratör eller funktionshanterare kan du undvika det här steget genom att aktivera funktionen **Aktivera omvärdering av bank utan parameter** på arbetsytan för **funktionshantering**.

> [!NOTE]
> Om en juridisk person använder en ryska, polska och ungerska lands-/regionskoder kan du redan göra bank – omräkning i utländsk valuta. Du kan inte använda omvärdering i utländsk valuta som används i andra länder eller regioner.

## <a name="process-foreign-currency-revaluation"></a>Bearbeta en omvärdering i utländsk valuta

När installationen är slutförd använder du sidan **omvärdering i utländsk valuta** för i kassa- och bankhantering för att omvärdera saldona för ett eller flera bankkonton i alla juridiska personer. Du kan köra processen i realtid eller schemalägga den för att köra med en batch.

Sidan **omvärdering i utländsk valuta** visar historiken för varje ombedömningsprocess. Den visas när processen kördes och vilka kriterier som har definierats och ger länkar till verifikationen som skapades för omvärderingen. Det visar också om en tidigare omvärdering återfördes. Om du vill köra ombedömningsprocessen väljer du **omvärdering i utländsk valuta** i åtgärdsfönstret för att öppna dialogrutan **Bank – omvärdering i utländsk valuta**.

Fältet **ombedömningsdatum** anger slutdatumet för beräkningen av den utländska valutabalans som ska omvärderas. Summan av alla banktransaktioner som uppstått genom detta datum omvärderas.

Fältet **valutakursdatum** anger den valutakurs som används för att omvärdera valutasaldona. Du kan t.ex. omvärdera saldon per den 31 januari men använder valutakursen som definierats för den 1 februari.

Ombedömningsprocessen kan köras för en eller flera juridiska personer. Sökningen visar endast de juridiska personer som du har tillgång till. Välj de juridiska personerna som du vill välja bankkonton som berättigar till omvärdering i utländsk valuta. Bankkonton för de juridiska personerna visas i rutnätet.

Ange alternativet **förhandsgranskning innan du bokför** till **Ja** om du vill visa resultaten av omvärderingen innan du bokför den. Omvärdering i utländsk valuta har en förhandsgranskning som kan bokföras. Du måste inte köra ombedömningsprocessen igen. Du kan exportera resultaten i förhandsgranskningen till Microsoft Excel om du vill behålla historiken för hur beloppen beräknades. Du kan inte använda batchbearbetning om du vill granska resultatet av omvärderingen.

Välj **OK** om du vill bearbeta omvärdering i utländsk valuta. En post skapas för att spåra historiken för varje körning. En separat post skapas för varje juridisk person och bokföringsskikt.

## <a name="calculate-unrealized-gainloss"></a>Beräkna orealiserad vinst/förlust

I kassa- och bankhantering anses bankvaluta vara basvalutan och omvärderas inte. Saldot på bankkontot i redovisningsvalutan omvärderas med valutakurser mellan bank- och redovisningsvalutan i **valutakursdatum**. Saldot på bankkontot i rapporteringsvalutan omvärderas också med valutakurser mellan bank- och rapporteringsvalutan i **valutakursdatum**.

En transaktion skapas för skillnaden mellan saldot på bankkontot och det nya saldot som beräknas för redovisningsvalutan. En annan transaktion skapas för skillnaden mellan saldot på bankkontot och det nya saldot som beräknas för rapporteringsvalutan. Posterna för dessa transaktioner markeras som avstämda. 

Inga poster görs för redovisningsvalutan om bankvalutan matchar redovisningsvalutan. På samma sätt görs inga poster för rapporteringsvalutan om bankvalutan matchar rapporteringsvalutan.

Transaktionen för omvärdering i utländsk valuta delas också upp mellan de dimensioner som finns på banktransaktionerna. Delningen baseras på saldot för varje dimension. Om till exempel totala saldot är 10 000, men saldot för affärsenhet 001 är 4 000, är saldot för affärsenhet 002 6 000. I det här fallet bokförs 40 procent av ombedömningsbeloppet på ombedömningskontot med affärsenhet 001 och 60 procent bokförs på ombedömningskontot med affärsenhet 002. Om kontostrukturen inte innehåller en affärsenhet bokförs hela beloppet på ombedömningskontot.

## <a name="reverse-foreign-currency-revaluation"></a>Återför omräkning i utländsk valuta

Om du måste återföra omvärderingtransaktionen, välj **Återför transaktion** på åtgärdsfönstret på sidan **Omräkning i utländsk valuta**. En historisk ny post om omräkning i utländsk valuta skapas för att bibehålla den historiska redovisningsspårningen för när omvärdering genomfördes eller återfördes.

Om du vill ångra flera omvärderingar måste du återföra den senaste omvärderingen först. Fortsätt att återföra tidigare omvärderingar i datumordning. Sedan kan du behandla nya omvärderingar för de perioder som du har återförts.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
