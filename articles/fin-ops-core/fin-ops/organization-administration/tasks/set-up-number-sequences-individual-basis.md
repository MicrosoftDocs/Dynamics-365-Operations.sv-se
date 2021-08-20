---
title: Ställa in enskilda nummerserier
description: Detta avsnitt förklarar hur man ställer in enskilda nummerserier.
author: sericks007
ms.date: 08/16/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: NumberSequenceTableListPage, NumberSequenceDetails
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 50f7f42f3d24a608d43cf7469a7624efe09a74db8f1d0fcd2704dedbd8f503be
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6749518"
---
# <a name="set-up-number-sequences-on-an-individual-basis"></a>Ställa in enskilda nummerserier

[!include [banner](../../includes/banner.md)]

Detta avsnitt förklarar hur man ställer in enskilda nummerserier. Nummerserier används för att generera läsliga, unika identifierare för huvuddataposter och transaktionsposter och som kräver dem. En huvuddata eller en transaktionpost som kräver en identifierare, kallas för en referens. Innan du kan skapa nya poster för en referens, måste du ställa in en nummerserie och koppla den till referensen. Du kan ställa in alla nödvändiga nummerserier samtidigt med hjälp av guiden **Ställa in nummerserier**, eller så kan du skapa eller ändra enskilda nummerserier med hjälp av formuläret Sidan **Nummerserier**.

1. Gå till **Navigeringsfönster > Moduler > Organisationsadministration > Nummerserier > Nummerserier**.
2. Välj **nummerserier**
3. Skriv ett värde i fältet **Nummerseriekod**.
4. Skriv ett värde i fältet **Namn**.
5. Välj ett omfång för nummerserien och de valda omfångvärdena från listrutan på snabbfliken **Områdesparametrar**. Omfånget definierar vilka organisationer använder nummerserien. Dessutom kan nummerserier som har ett annat omfång än **Delad** ha segment som motsvarar deras omfång. Till exempel kan en nummerserie med omfånget **Juridisk person** innehålla ett segment med en juridisk person. Mer information om omfång finns i hjälpavsnittet [Översikt över nummerserier](../number-sequence-overview.md). 
6. Expandera avsnittet **Segment**.
    - Definiera formatet för nummerserien genom att lägga till, ta bort och ordna om segment.  
    - Nummerserier för alla områden kan innehålla *Konstanta segment* och *Alfanumeriska segment*. Konstanta segment innehåller en uppsättning alfanumeriska tecken som inte ändras. Använd den här segmenttypen om du vill lägga till ett bindestreck eller andra avgränsare mellan nummerseriesegment. Alfanumeriska segment innehåller en kombination av nummertecken (#) och et-tecken (&). Dessa representerar bokstäver och siffror som ökar varje gång som ett nummer i serien används. Använd ett nummertecken (#) om du vill ange att öka nummer och en et-tecken (&) om du vill ange att öka bokstäver. Med formatet `#####_2014` skapas till exempel serien `00001_2014`, `00002_2014`, osv. Minst ett alfanumeriskt segment måste vara närvarande. Omfångsegment som till exempel företag eller juridisk person, är inte obligatoriska. Men om du inte inkluderar omfångsegment i formatet, genereras ändå nummer för den valda referensen per omfång.  
7. Visa avsnittet **Referenser**. Välj dokumenttyp eller post för att tilldela denna nummerserie. Detta steg är valfritt för följder som definierats för särskilda ansökninganvändningmönster. I dessa situationer genereras ett nytt nummer, med hjälp av värdet av en nummerseriekod eller ett ID, utan att använda en referens. Ett exempel på ett särskilt ansökninganvändningmönster är en verifikationsserie som används för specifika journalnamnet. Men vi rekommenderar att du inte använder sådana mönster.  
8. Expandera den **allmänna** delen. Ange om nummerserien är manuell och kontinuerlig eller ickekontinuerlig på snabbfliken Allmänt. Ange även lägsta och högsta numret som kan användas i nummerserien. Vi rekommenderar inte att ändra en löpande nummerserie till en kontinuerlig nummerserie. Nummerserien kommer inte att vara korrekt kontinuerlig. Den här ändringen kan även orsaka dubbelnyckelkränkningar i databasen. Dessutom har kontinuerliga nummerserier en större effekt på systemets prestanda.   
9. Klicka på **Spara**.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
