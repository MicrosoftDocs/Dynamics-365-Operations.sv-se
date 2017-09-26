---
title: "Blandad planering - Kombinera diskret, process- och lean-försörjning"
description: "Det här avsnittet innehåller information om läget för blandad planering. I läget för blandad planering kan du utforma din leveranskedja baserat på materialflödet. Microsoft Dynamics 365 for Finance and Operations ser till att materialflödet följer dina modeller, oavsett vald leveranspolicy (kanban, produktionsorder, inköpsorder, batchorder eller överföringsorder)."
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResStorageDimensionGroup, InventItemOrderSetup, ReqItemTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 52931
ms.assetid: 2e8b5fd1-cee9-45da-a3ae-6961fb020b89
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 9dbbe540c919d27bafcc10614f308e5b6ba313f1
ms.contentlocale: sv-se
ms.lasthandoff: 06/13/2017

---

# <a name="mixed-mode-planning---combine-discrete-process-and-lean-sourcing"></a>Blandad planering - Kombinera diskret, process- och lean-försörjning

[!include[banner](../includes/banner.md)]


Det här avsnittet innehåller information om läget för blandad planering. I läget för blandad planering kan du utforma din leveranskedja baserat på materialflödet. Microsoft Dynamics 365 for Finance and Operations ser till att materialflödet följer dina modeller, oavsett vald leveranspolicy (kanban, produktionsorder, inköpsorder, batchorder eller överföringsorder). 

Du kan välja din övergripande strategi för att leverera en produkt, oavsett produktstrukturen.  

Du kan till exempel ha kanban i församlingen, där material köps för montering av produktionsorder, kanban, överföringar, batch beställningar, eller någon kombination som är lämpliga för din supply chain, men du kan fortfarande ha full överblick över förbrukningsmaterial. Denna förmåga leder till optimerad supply chain processer och förbättrad synlighet in i leveranskedjan.  

Granulariteten av utbudspolicy som används i huvudplanering beror på lagring dimensioner som är aktiverade som täckning måtten. Om du vill aktivera huvudplanering för återfyllning och utbudet av olika typer av platser (t.ex. genom att separera fabriksgolvet för olika produktionsenheter, eller genom att separera olika typer av material och färdiga varor lagerlokaler), rekommenderar vi att du aktiverar ort och lager som täckning måtten. Alternativt kan lagret kan uteslutas som en täckning dimension. I så fall, när du använder avancerad lagerhantering, alla rörelser inuti ett lager styrs av lagerarbetet, medan alla rörelser över lager kan styras genom tillbakadragande kanban.

## <a name="supply-policies"></a>Utbudspolicyn
Blandad planering i Finance and Operations styr hur produkten levereras samt (baserat på tillgång) hur härledda krav (förbrukning av artiklar från en strukturlista \[BOM\]) utfärdas. Baserat på vilken typ av order automatiskt källor material som matchar kraven.  

Utbudspolicyn kan definieras på produktnivå eller vid någon finkornighet som stöder dina krav. Du definierar granulariteten i utbudspolicyer på **Standard för inställningar** sidan.  

Utbudspolicyn kan styras av produkten, dimensioner (konfiguration, färg och storlek), ort och lager. Denna inställning görs på **posten täckning** sida.  

Den standardinställda ordertypen styr i vilken ordning huvudplanering genererar.  

Oavsett hur leveranskedjan har modellerats stöder Finance and Operations din blandade leveranspolicy. Du kan ha en order som hämtas från kanban. Alternativt kan du ha en kull order som kräver en produkt som levereras genom överföringar eller kanban.  

Finance and Operations ser till att materialflödet följer modellen.  

Lagret för att plocka material tilldelas dynamiskt vid tiden efter policyn har definierats.  

Typiskt, kanban är inte skapt för framtida datum, eftersom en kanban har en kort livslängd. För att upprätthålla full insyn i supply chain, vi har infört den nya planeringen begreppet "planerade kanban", som används för att beräkna härledda behov och hjälper till att säkra att vattenkraftproduktion bygger på samma logik som används när den faktiska kanban skapas.  

Samma logik föreligger för alla andra typer av policy. Därför långsiktiga material planering baseras på samma logik som du förväntar dig att köra med verkliga order efter produktion och leverans är godkända.

## <a name="materials-allocation-crosssupply-policy--resource-consumption-on-boms"></a>Tvärleveranspolicy för materialfördelning – Resursförbrukning i strukturlistor
Resursförbrukning är en viktig funktion. Resursförbrukning gör ett lager för att plocka material väljas dynamiskt baserat på policyn (typ), och också gör underhållet av bas data enklare.  

Resursförbrukning kräver att lagret att material plockas från tilldelas baserat på det sätt som produkten levereras. Med andra ord, kör helst systemet hittar de resurser som ska användas för tillverkning. Baserat på dessa resurser, därefter finner plockar lager.  

För arbete som är oberoende av policyn, behöver du inte ändra informationen på BOM om matningen har ändrats. För ad hoc-förändringar ser Finance and Operations till att material köps in från rätt lager.

## <a name="process-manufacturing--the-production-type"></a>Process manufacturing – produktion typ
För fullständig flexibilitet i blandat läge rekommenderar vi att du använder strukturlistor av produktionstyp för alla produkter. Du kan sedan använda produktionsorder, överföringsorder, kanbans eller inköpsorder för att tillhandahålla en produkt. Process manufacturing, måste du använda en typ av **formel**, **Co-produkt**, **biprodukt** eller **planering**. Kanban och produktionsorder kan inte användas för dessa typer av produktion.



