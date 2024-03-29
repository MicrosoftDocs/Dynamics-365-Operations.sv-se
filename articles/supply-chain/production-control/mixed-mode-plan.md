---
title: Blandad planering – Kombinera diskret, process- och lean-försörjning
description: Denna artikel innehåller information om läget för blandad planering.
author: johanhoffmann
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResStorageDimensionGroup, InventItemOrderSetup, ReqItemTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 52931
ms.assetid: 2e8b5fd1-cee9-45da-a3ae-6961fb020b89
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 335bdc9690b3111f4a04adc7e82d62de36ff4caf
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9066001"
---
# <a name="mixed-mode-planning---combine-discrete-process-and-lean-sourcing"></a>Blandad planering – Kombinera diskret, process- och lean-försörjning

[!include [banner](../includes/banner.md)]

Denna artikel innehåller information om läget för blandad planering. I läget för blandad planering kan du utforma din leveranskedja baserat på materialflödet. Dynamics 365 Supply Chain Management ser till att materialflödet följer dina modeller, oavsett den valda leveranspolicyn (kanban, produktionsorder, inköpsorder, batchorder eller överföringsorder). 

Du kan välja din övergripande strategi för att leverera en produkt, oavsett produktstrukturen.  

Du kan till exempel ha kanban i församlingen, där material köps för montering av produktionsorder, kanban, överföringar, batch beställningar, eller någon kombination som är lämpliga för din supply chain, men du kan fortfarande ha full överblick över förbrukningsmaterial. Denna förmåga leder till optimerad supply chain processer och förbättrad synlighet in i leveranskedjan.  

Granulariteten av utbudspolicy som används i huvudplanering beror på lagring dimensioner som är aktiverade som täckning måtten. Om du vill aktivera huvudplanering för återfyllning och utbudet av olika typer av platser (t.ex. genom att separera fabriksgolvet för olika produktionsenheter, eller genom att separera olika typer av material och färdiga varor lagerlokaler), rekommenderar vi att du aktiverar ort och lager som täckning måtten. Alternativt kan lagret kan uteslutas som en täckning dimension. När du använder avancerad lagerstyrning (WMS) kommer därför alla rörelser inuti ett lager att styras av lagerarbetet, medan alla rörelser mellan lager kan styras genom uttagskanban.

## <a name="supply-policies"></a>Utbudspolicyn
Blandad planering styr hur produkten levereras samt (baserat på tillgång) hur härledda krav (förbrukning av artiklar från en strukturlista \[BOM\]) utfärdas. Baserat på vilken typ av order automatiskt källor material som matchar kraven.  

Utbudspolicyn kan definieras på produktnivå eller vid någon finkornighet som stöder dina krav. Du definierar granulariteten i utbudspolicyer på **Standard för inställningar** sidan.  

Utbudspolicyn kan styras av produkten, dimensioner (konfiguration, färg och storlek), ort och lager. Denna inställning görs på **posten täckning** sida.  

Den standardinställda ordertypen styr i vilken ordning huvudplanering genererar.  

Oavsett hur leveranskedjan har modellerats stöder Supply Chain Management din blandade leveranspolicy. Du kan ha en order som hämtas från kanban. Alternativt kan du ha en kull order som kräver en produkt som levereras genom överföringar eller kanban.  

Supply Chain Management ser till att materialflödet följer modellen.  

Lagret för att plocka material tilldelas dynamiskt vid tiden efter policyn har definierats.  

Typiskt, kanban är inte skapt för framtida datum, eftersom en kanban har en kort livslängd. För att upprätthålla full insyn i supply chain, vi har infört den nya planeringen begreppet "planerade kanban", som används för att beräkna härledda behov och hjälper till att säkra att vattenkraftproduktion bygger på samma logik som används när den faktiska kanban skapas.  

Samma logik föreligger för alla andra typer av policy. Därför långsiktiga material planering baseras på samma logik som du förväntar dig att köra med verkliga order efter produktion och leverans är godkända.

## <a name="materials-allocation-cross-supply-policy--resource-consumption-on-boms"></a>Material fördelning cross-policy – Resursförbrukning för produktstrukturer
Resursförbrukning är en viktig funktion. Resursförbrukning gör ett lager för att plocka material väljas dynamiskt baserat på policyn (typ), och också gör underhållet av bas data enklare.  

Resursförbrukning kräver att lagret att material plockas från tilldelas baserat på det sätt som produkten levereras. Med andra ord, kör helst systemet hittar de resurser som ska användas för tillverkning. Baserat på dessa resurser, därefter finner plockar lager.  

För arbete som är oberoende av policyn, behöver du inte ändra informationen på BOM om matningen har ändrats. För ad hoc-förändringar ser Supply Chain Management till att material köps in från rätt lager.

## <a name="process-manufacturing--the-production-type"></a>Process manufacturing – produktion typ
För fullständig flexibilitet i blandat läge rekommenderar vi att du använder strukturlistor av produktionstyp för alla produkter. Du kan sedan använda produktionsorder, överföringsorder, kanbans eller inköpsorder för att tillhandahålla en produkt. Process manufacturing, måste du använda en typ av **formel**, **Co-produkt**, **biprodukt** eller **planering**. Kanban och produktionsorder kan inte användas för dessa typer av produktion.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]