---
title: Arbetsyta för hantering av anläggningstillgångar
description: Det här ämnet innehåller information om arbetsyta för anläggningstillgångar. Den här arbetsytan visar information som är relaterad till anläggningstillgångar som har registrerats i systemet. Den innehåller en sammanfattningsvy och en analysvy.
author: saraschi2
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetWorkspace
audience: Application User
ms.reviewer: roschlom
ms.assetid: ''
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 66c8d40aae65d48bea2f975432e6ec8ad741c76f
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5826820"
---
# <a name="fixed-asset-management-workspace"></a>Arbetsyta för hantering av anläggningstillgångar

[!include [banner](../includes/banner.md)]

Arbetsytan **anläggningstillgångar** visar information som är relaterad till anläggningstillgångar som har registrerats i systemet. Den här arbetsytan innehåller en sammanfattningsvy och en analysvy. Fliken **Mitt arbete** visar sammanfattningsrutor, information om anläggningstillgångar och information om anläggningstillgångar i det aktuella företaget. Du kan också lägga till analys till Power BI analysavsnittet direkt på arbetsytan. Fliken **Analys – alla företag** använder funktionerna i Microsoft Power BI för att visa visuella som är relaterade till anläggningstillgångar i alla företag.

## <a name="my-work"></a>Mitt arbete

### <a name="summary"></a>Sammanfattning

Rutorna i avsnittet **sammanfattning** ger en översikt över anläggningstillgångarna. Informationen inkluderar mått om tillgångar som ännu inte har förvärvats, tillgångar som förvärvats under innevarande år och tillgångar som har avyttrats under det innevarande året. Avsnittet **sammanfattning** har också snabbnavigering till listsidan **anläggningstillgång** och batchavskrivningsförslag och anläggningstillgångsjournal.

### <a name="find-fixed-assets"></a>Sök anläggningstillgångar

Avsnittet **hitta anläggningstillgångar** låter dig snabbt söka efter resurser med anläggningstillgångsnummer, grupp, namn, plats eller person som är ansvarig. Alla tillgångar som matchar sökvillkoren visas i listan.

Du kan visa följande sidor i listan:

 - Sidan **Detaljer** för anläggningstillgången.
 - Sidan **Böcker** för alla böcker som associeras med anläggningstillgången
 - Sidan **Anläggningstillgångvärderingar**

### <a name="valuations"></a>Värderingar

Sidan **anläggningstillgångvärderingar** låter dig visa den viktigaste informationen om en anläggningstillgång på en sida och även uppgifter för alla böcker som associeras med anläggningstillgången. Alternativet **saldon** längst upp till vänster på sidan visar den aktuella värderingen för varje bok som associeras med anläggningstillgången. Du kan gå tillbaka från värdena för att visa de detaljerade transaktioner som utgör sammanfattningsvärdet. Alternativet **profil** längst upp till vänster på sidan visar avskrivningstidsplanen för varje bok som associeras med anläggningstillgången.

Du kan komma åt sidan **Anläggningstillgångvärderingar** från arbetsytan **Anläggningstillgånghantering** eller listsidan **Anläggningstillgång**.

### <a name="related-information"></a>Relaterad information

Du kan gå direkt till sidan **Bokinställningar**, sidan **Fråga om transaktioner med anläggningstillgångar** och flera rapporter med hjälp av länkarna i delen **relaterad information** i arbetsytan.

### <a name="analytics--all-companies"></a>Analyser – alla företag

Sidan **analys** ger viktiga mått om anläggningstillgångar för alla juridiska personer i systemet. Åtkomst till den här fliken styrs av vyn anläggningstillgångsanalyser för alla företags säkerhetsprofil.

Följande tabell visar de visulaiseringar som är tillgängliga på varje rappportsida.

| Rapportsida            | Visualisering        |
|------------------------|----------------------|
| Anläggningstillgångvärderingar | Totalt bokfört nettovärde |
| Anläggningstillgångvärderingar | Bokfört nettovärde efter anläggningstillgångsgrupp |
| Anläggningstillgångvärderingar | Anskaffningsvärden |
| Anläggningstillgångvärderingar | Avyttrade värden |
| Anläggningstillgångvärderingar | Information om anläggningstillgångar |
| Bedömningskartor        | Totalt bokfört nettovärde |
| Bedömningskartor        | Placeringar för anläggningstillgång |
| Bedömningskartor        | Information om anläggningstillgångar |

Om du vill visa analysen med data måste du först uppdatera det sammanlagda måttet AssetTransactionMeasure på sidan **enhetslagring**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]