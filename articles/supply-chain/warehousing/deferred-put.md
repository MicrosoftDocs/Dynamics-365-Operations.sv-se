---
title: Uppskjuten bearbetning av lagerhållningsarbete
description: I denna artikel beskrivs de funktioner som gör att uppskjuten bearbetning av lagerställets arbetsplaceringsåtgärder är tillgängliga i Dynamics 365 Supply Chain Management.
author: Mirzaab
ms.date: 11/18/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWorkProcessingPolicy, WHSWorkDeferredPutProcessingTask
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2019-6-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: f4eeea0805c2cecedbd6b42926191ab02022df9f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8899307"
---
# <a name="deferred-processing-of-warehouse-work"></a>Uppskjuten bearbetning av lagerhållningsarbete

[!include [banner](../includes/banner.md)]

I denna artikel beskrivs de funktioner som gör att uppskjuten bearbetning av placeringsåtgärder för lagerställearbete i Dynamics 365 Supply Chain Management.

Funktionen uppskjuten bearbetning låter lagerarbetare fortsätta att göra annat arbete medan placeringsåtgärden bearbetas i bakgrunden. Uppskjuten bearbetning är användbart när många arbetsrader måste bearbetas och arbetaren kan låta det arbetet bearbetas asynkront. Det är också användbart när servern kan ha ad hoc- eller oplanerade ökningar i bearbetningstiden, och den ökade bearbetningstiden kan påverka användarens produktivitet.

Bakgrundsbearbetning uppnås med hjälp av SysOperation-ramverket. Mer information finns i [Översikt över SysOperation-ramverk](/dynamicsax-2012/developer/sysoperation-framework-overview).

## <a name="configuring-the-work-processing-policies"></a>Konfigurera arbetsbearbetningspolicyer

Om du vill använda uppskjuten bearbetning måste du konfigurera och använda en policy för bearbetning av arbete.

Policyer konfigureras på sidan **arbetsbearbetningspolicyer**. Följande register beskriver de fält som är tillgängliga på den sidan.

| Fält                           | Beskrivning |
|---------------------------------|-------------|
| Namn på arbetsprocesspolicy     | Namnet på arbetsbearbetningspolicyn. |
| Typ av arbetsorder                 | Den arbetsordertyp som policyn tillämpas på. |
| Åtgärd                       | Åtgärden som bearbetas med hjälp av policyn. |
| Arbetsprocessmetod          | Den metod som används för att bearbeta arbetsraden Om metoden är inställd på **omedelbar**, liknar beteendet det beteende när inga policyer för bearbetning av arbetsprocesser används för att bearbeta raden. Om metoden har ställts in på **uppskjuten**, används uppskjuten bearbetning som använder batchramverket. |
| Tröskelvärde för uppskjuten bearbetning   | Värdet **0** (noll) innebär att det inte finns något tröskelvärde. I det här fallet används uppskjuten bearbetning om den kan användas. Om den specifika beräkningen av tröskelvärde ligger under tröskelvärdet används metoden omedelbar. I annat fall används den uppskjutna metoden om den kan användas. För försäljnings- och överföringsrelaterat arbete beräknas tröskelvärdet som antalet associerade källbeläggningsrader som bearbetas för arbetet. För lagerpåfyllnadsarbete beräknas tröskelvärdet som antalet arbetsrader som fylls på av arbetet. Genom att ange ett tröskelvärde på till exempel **5** för försäljning, kommer mindre arbeten som har färre än fem inledande källbeläggningsrader inte att använda uppskjuten bearbetning, men större arbeten kommer att använda den. Tröskelvärdet har endast effekt om arbetsbearbetningsmetoden har ställts in på **uppskjuten**. |
| Batchgrupp för uppskjuten bearbetning |Den batchgrupp som används för bearbetning. |

För uppskjuten bearbetning kan följande arbetsordertyper användas: försäljningsorder, problem med överföringsorder och påfyllning.

## <a name="assigning-the-work-creation-policy"></a>Tilldela policyn för skapande av arbete

Policyn för skapande av arbete kan tilldelas i parametrarna för lagerstyrning. Den kan också tilldelas på nivån för enskilda lagerställen. Om policyn tilldelas ett lagerställe, tillämpas den endast på arbete som skapas för det lagerstället. Om ingen policy har tilldelats på lagerställenivå tillämpas policy från parametrarna för lagerställehantering.

## <a name="viewing-the-deferred-put-processing-tasks"></a>Visa uppgifter om uppskjuten placeringsbearbetning

Du kan visa uppskjutna placeringsbearbetningsuppgifter på sidan **uppskjutna placeringsbearbetningsuppgifter**.

Som standard visas aktiviteterna **slutförda**.

| Fält            | Beskrivning |
|------------------|-------------|
| Status           | Uppgiftens status. |
| Batchjobbstatus | Statusvärdet för det relaterade batchjobbet. Om batchjobbet har bearbetats innehåller batchhistoriken loggen och information från batchjobbet. |

Här följer en förklaring av möjliga statusar:

- **Väntar** – det relaterade batchjobbet väntar på bearbetning på batchservern.
- **Misslyckades** – bearbetningen misslyckades. Aktiviteten kan ombearbetas med hjälp av **Bearbeta uppskjuten placering** eller den kan avbrytas med hjälp av åtgärd **Avbryt uppskjuten placering**.
- **Slutförd** – jobbet slutfördes.

## <a name="impact-on-closed-work-dates"></a>Påverkan på stängda arbetsdatum

När uppskjuten placeringsbearbetning används anges det stängda arbetsdatumet som det skapade datumet/tiden för de uppskjutna placeringsbearbetningsuppgifterna. Det stängda arbetsdatumet används eftersom det är den bästa uppskattningen för när placeringsåtgärden slutfördes.

## <a name="reprocessing-a-failed-task"></a>Ombearbetning av en misslyckad uppgift

Du kan ombearbeta en misslyckad uppgift genom att markera den på sidan och sedan välja **bearbeta uppskjuten placering**. Ombearbetning motsvarar en situation där användaren slutför artikelinförsel från den mobila enheten som om den var inställd för omedelbar bearbetning.

## <a name="canceling-failed-tasks"></a>Avbryter misslyckade aktiviteter

Endast misslyckade aktiviteter kan avbrytas. När du avbryter en aktivitet kan du tilldela den till en ny användare. Aktiviteten kan också förbli tilldelad till den användare som bearbetade arbetet. Annullering motsvarar en situation där arbetet förs tillbaka till den mobila enheten som om det sista plockningssteget bara slutfördes och arbetet måste föras bort. Användaren kan dock bestämma att arbetet är "annorlunda" eftersom det bara har ett artikelinlagringssteg och platsen kommer att motsvara den plats som den första användaren som bearbetade arbetet hade som en slutlig plats.

När en aktivitet avbryts, blockeras arbetet inte längre av orsaken till den uppskjutna placeringsbearbetningen. Den kan bearbetas på nytt med hjälp av den mobila enheten.

Uppgiftsposten tas bort när aktiviteten avbryts.

## <a name="configuring-the-mobile-device-menu-to-skip-the-deferred-processing-policy"></a>Konfigurera menyn för mobila enheter för att hoppa över den uppskjutna bearbetningspolicyn

Du kan konfigurera menyalternativet för mobila enheter så att policyn för uppskjuten bearbetning inte används. Arbetet bearbetas sedan som det är när ingen policy för uppskjuten bearbetning används. Med den här funktionen kan en arbetsledare använda ett specifikt menyalternativ där uppskjuten placering inte används. Om du vill konfigurera den ställer du in fältet **Policy för uppskjuten placeringsbearbetning** till **Åsidosätt inställningar och bearbeta placering synkront**. 

## <a name="restrictions-when-the-deferred-put-processing-isnt-applied"></a>Begränsningar när uppskjuten placeringsbearbetning inte tillämpas

Det finns flera scenarier där uppskjuten placeringsbearbetning inte tillämpas även om policyn har konfigurerats. Nedan följer några exempel:

- Manuell komplettering av arbetet används.
- Arbetet slutförs med hjälp av automatisk komplettering.
- Granskningsmallar används.


## <a name="monitoring-the-deferred-processing-tasks-from-the-outbound-work-monitoring-workspace"></a>Övervaka uppskjutna bearbetningsuppgifter från arbetsytan utgående arbetsövervakning

**Arbetsytan utgående arbetsövervakning** har två paneler som hjälper dig att övervaka uppskjutna placeringsbearbetningsuppgifter:

- **Misslyckade uppskjutna placeringsbearbetningsuppgifter** – den här panelen visar antalet misslyckade aktiviteter. Om det finns misslyckade aktiviteter måste lagerchefen antingen bearbeta om dem eller avbryta dem, eftersom de inte kommer att bearbetas om automatiskt.
- **Väntar på uppskjutna placeringsbearbetningsuppgifter** – den här panelen visar antalet aktiviteter som har varit i status **Väntar** i mer än 10 minuter. Om panelen visar ett tal, kan det tyda på att ett problem uppstod under batchbearbetning. Du kan bearbeta de **väntade** uppgifterna manuellt. Om batchjobbet för en uppgift bearbetas senare kommer det bara att misslyckas, eftersom det redan har bearbetats. Det blir ingen påverkan.

## <a name="deleting-completed-tasks"></a>Ta bort slutförda uppgifter

Du kan ta bort uppskjutna placeringsbearbetningsuppgifter som har slutförts genom att markera dem och ta bort dem på sidan.

## <a name="additional-resources"></a>Ytterligare resurser

- [Uppskjuten bearbetning av manuell åtgärd för lagerrörelse](deferred-processing-manual-inventory-movement.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]