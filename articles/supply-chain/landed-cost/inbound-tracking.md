---
title: Spåra inkommande färder och leveransbehållares resor
description: I det här avsnittet beskrivs hur du kan använda sidan inkommande spårning för att spåra förloppet för dina färder och leveransbehållares resor.
author: Weijiesa
ms.date: 01/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMContainerActivityTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 07f93cfe563c90d06dd73d46bad678a11a51c5eb
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/04/2022
ms.locfileid: "8693456"
---
# <a name="track-inbound-voyages-and-shipping-container-journeys"></a>Spåra inkommande färder och leveransbehållares resor

[!include [banner](../../includes/banner.md)]

Sidan **Inkommande spårning** gör att du kan använda sidan inkommande spårning för att spåra förloppet för dina färder och leveransbehållares resor. Varje färd och resa delas upp av *aktiviteter*, som vart och ett har sin egen rad på sidan. På sidan kan du visa och ange uppskattade datum och faktiska datum per aktivitet.

Dessa aktiviteter visar normalt, beroende på inställningarna i [spårningskontrollcentret](delivery-information-setup.md#tracking-control-center) automatiskt det uppskattade landningsdatumet vid slutdestinationen. Beroende på inställningarna uppdaterar vanligen slutdatumet leveransdatumet eller det bekräftade datumet på inköpsorderraderna. För överföringsorderrader kan du ställa in att systemet ska uppdatera inleveransdatumet.

För att öppna sidan **Inkommande spårning**, gå till **Hemtagningskostnad \> Spårning \> Inkommande spårning**.

## <a name="filter-the-activities-list"></a>Filtrera aktivitetslistan

Du kan använda fälten **Färd** och **Leveransbehållare** längst upp på sidan **Inkommande spårning** för att filtrera sidan så att den bara visar aktiviteter som är associerade med den valda färden och/eller leveransbehållaren.

## <a name="update-tracking-information"></a>Uppdatera uppföljningsinformation

Om du vill uppdatera schemat för en färd eller resa anger du startdatum för den första aktiviteten. Det uppskattade slutdatumet för den senaste aktiviteten uppdateras sedan. Inställningarna för varje strecka och färdmall för [spårningskontrollcentret](delivery-information-setup.md#tracking-control-center) avgör de uppskattade ledtiderna. De uppskattade slutdatumen använder ledtiden från aktivitetens startdatum. När det faktiska slutdatumet registreras uppdateras sedan startdatumet för nästa aktivitet till samma datum som föregående aktivitets faktiska slutdatum. Den faktiska ledtiden uppdateras så att jämförelse och analys kan göras. Ytterligare noteringar kan anges i fältet **Observera**.

Ordningen på aktiviteterna i rutnätet bestäms av ordningen för den aktuella färdmallen. Om sträckornas ordning i den bifogade färden ändras kommer även spårningskontrollen att ändras.

Du kan uppdatera datumen för alla behållare genom att välja **Uppdatera startdatum** eller **Uppdatera det faktiska slutdatumet** i åtgärdsfönstret. Du kan även ange datum per behållare i försändelsen. Det här arbetssättet medger större flexibilitet eftersom behållare kan delas upp i en miljö med flera resor.

## <a name="buttons-on-the-action-pane"></a>Knappar i åtgärdsfönstret

Du kan använda knapparna på åtgärdsfönstret på sidan **inkommande spårning** när du vill arbeta med inkommande färder och resor. I följande tabell beskriver de knappar som är tillgängliga.

| Knapp | beskrivning |
|---|---|
| Redigera | Redigera en färd eller resa med leveransbehållare. |
| Nytt | Skapa en ny färd eller resa med leveransbehållare. |
| Radera | Radera en vald färd eller resa med leveransbehållare. |
| Uppdatera startdatum | Uppdatera startdatum för en aktivitet för alla behållare i en färd. När startdatumet för en viss aktivitet eller sträcka av en sådan resa, uppdateras de uppskattade startdatumen baserat på angiven ledtid. |
| Uppdatera faktiskt slutdatum | Uppdatera slutdatum för en aktivitet för alla behållare i en färd. När slutdatumet för en specifik aktivitet uppdateras uppdateras de efterföljande aktiviteterna baserat på den angivna ledtiden. |
| Lägg till aktiviteter | Lägga till en aktivitet till en färd manuellt. Du kan till exempel lägga till desinfektionsaktivitet. Tillägget kan medföra att det bekräftade leveransdatumet för varorna i fartyget eller det fartyget eller färd måste ändras. När en aktivitet läggs till i färden, anges inte de uppskattade dagarna förrän startdatumet för en färdsträcka uppdateras. |

## <a name="information-and-settings-on-the-overview-tab"></a>Information och inställningar på fliken Översikt

Fliken **Översikt** visar en lista över alla aktiviteter som tillhör den färden och/eller leveransbehållare som valts längst upp på sidan. Följande register beskriver de fält som är tillgängliga för varje aktivitet.

| Fält | beskrivning |
|---|---|
| Etapp | Mallens ID för aktiviteten, enligt definitionen i mallen. |
| Leveranssätt | Den förväntade leveransmetoden för aktiviteten. |
| Aktivitet | Det här fältet identifierar vanligtvis jobbet eller uppgiften som är kopplad till aktiviteten. Typiska exempel inkluderar *Segling* och *Clearance*. |
| beskrivning | En längre beskrivning av aktivera. |
| Startdatum | Detta fält visar initialt det beräknade startdatumet för aktiviteten. Efter att du registrerat det faktiska slutdatumet för den föregående aktiviteten, visar det det faktiska startdatumet. Det här fältet används för att bestämma uppskattat slutdatum, baserat på ledtiden. |
| Uppskattat slutdatum | Värdet i det här fältet beräknas baserat på startdatum och ledtid. Vanligtvis redigerar du inte värdet direkt. |
| Faktiskt slutdatum | En användare bör uppdatera fältet så snart som möjligt efter att aktiviteten har inträffat. Den faktiska ledtiden uppdateras sedan. |
| Uppskattade dagar | Den beräknade tiden (i dagar) som krävs för att slutföra aktiviteten. |
| Faktiska dagar | Den faktiska tiden (i dagar) som krävs för att slutföra aktiviteten. |
| Sedel | Använd det här fältet när du vill lägga till anteckningar och detaljer om aktiviteten. |

## <a name="information-and-settings-on-the-general-tab"></a>Information och inställningar på fliken Allmänt

Fliken **Allmänt** visar information om den del som valts på fliken **Översikt**. Trots att en del av informationen som visas på fliken **Översikt** upprepas innehåller den även ytterligare information om det valda avsnittet.
