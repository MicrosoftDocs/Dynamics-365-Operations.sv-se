---
title: Krav för översikt över standardkostnader
description: I denna artikel beskrivs grundläggande steg för hur du använder standardkostnader.
author: JennySong-SH
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: InventStdCostConv, CostingVersion
audience: Application User
ms.reviewer: kamaybac
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yanansong
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2c36ebe0957cff85fff6af1d979503f9e6e60d28
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9066743"
---
# <a name="prerequisites-for-standard-costs-overview"></a>Krav för översikt över standardkostnader

[!include [banner](../includes/banner.md)]

I denna artikel beskrivs grundläggande steg för hur du använder standardkostnader. Efterföljande steg beror på företagets verksamhet. Vilka steg som ska användas skiljer sig beroende på företagets verksamhet, till exempel om det är en miljö utan tillverkning, en tillverkningsmiljö utan flöden eller en tillverkningsmiljö med flöden. 

Så här ställer du in standardkostnader.

**1. Skapa en artikelmodellgrupp för standardkostnader.**

Använd **artikelmodellgruppen** om du vill skapa en ny grupp för standardkostnader och tilldela lagermodellen **standardkostnad**. Artikelmodellgruppens ID ska ha en innebörd, till exempel **Stdkost**. Markera kryssrutorna om du vill ange att gruppen ska tillåta ekonomiskt negativt lager och att den ska bokföra fysiskt lager och ekonomiskt lager. Denna standardkostnadsgrupp tilldelas artiklar.

**2. Definiera redovisningskonton som hör till standardkostnadsavvikelser.** 

Använd sidan **Kontoplan** om du vill definiera huvudbokskonton som hör till standardkostnadsavvikelser. Dessa huvudbokskonton måste definieras innan de kan tilldelas på sidan **Posting**. Redovisningskontona kan återspegla artikelgrupper och kostnadsgrupper.

**3. Tilldela huvudbokskonton till artikelbokföringar som hör till standardkostnadsavvikelser.** 

Använd sidan **Posting** om du vill tilldela huvudbokskonton som hör till standardkostnadsavvikelser. Du kan välja om du vill ange en avvikelses redovisningskonto per artikel (eller artikelgrupp) och per kostnadsgrupp (eller kostnadsgruppstyp), eller specificera att redovisningskontot gäller för alla artiklar och alla kostnadsgrupper. Dessa val motsvarar kostnadsrelationer för tabeller, grupper och allt. 

Använd sidan **Transaktionskombinationer** om vill du göra det möjligt att använda kostnadsrelationer (för tabeller, grupper och allt) innan du definierar artikelbokföringsregler.

**4. Definiera lagerparametrar som hör till standardkostnader.** 

-  Använd fliken **Lagerredovisning** på sidan **Lagerredovisningsparametrar** om du vill definiera två kontrollparametrar som hör till standardkostnader.

    -  I fältet **Kostnadsuppdelning** välj **Inga** eller **Delredovisning**. Om du väljer **Delredovisning** är kostnadsuppdelningen *aktiv*. En aktiv kostnadsuppdelning har stor betydelse när du beräknar, behåller och visar kostnadsgruppssegmentering över en produktstruktur i flera nivåer för standardkostnadsartiklar. När kostnadsuppdelningen är aktiv kan du rapportera och analysera lager, produkter i arbete (PIA) och kostnader för sålda varor (COGS) per kostnadsgrupp på en enda nivå, flera nivåer eller i totalformat. Om kostnadsuppdelningen är aktiv och du också aktiverar en tillverkad artikels kostnad kommer kostnadsgruppssegmenteringen att lagras i artikelns kostnadspost. 

    -  Om du väljer **ingen** underhålls inte kostnadsgruppssegmenteringen för standardkostnadsartiklar. Med andra ord beräknas och underhålls en tillverkad artikels standardkostnad som ett enskilt belopp, utan kostnadsgruppssegmentering. Kostnadsbidragen från tillverkade komponenter aggregeras till ett enda belopp.

-  Använd fältet **Avvikelser från standard** välj **Summerat** eller **Per kostnadsgrupp**. Om du väljer **Per kostnadsgrupp** kan du identifiera inköpsprisavvikelser och produktionsavvikelser per kostnadsgrupp. Du kan även identifiera fyra typer av produktionsavvikelser: partistorlek, kvantitet, pris och ersättning. Om du väljer **summerad** kan du inte identifiera avvikelser per kostnadsgrupp, och du kan inte identifiera de fyra typerna av produktionsavvikelse. Du kan endast visa en summerad produktionsavvikelse.

-  Principen om avvikelse från standarden fungerar oberoende av kostnadsuppdelningsprincipen. Med andra ord innebär det att du kan välja en kostnadsuppdelningsprincip som är **ingen**, och välja avvikelser per kostnadsgrupp, så att produktionsavvikelser per kostnadsgrupp ändå kan fångas in.

**5. Skapa kostnadsversioner för standardkostnader.** 

Använd sidan **Inställningar för kostnadsredovisningsversion** om du vill skapa en eller flera kostnadsversioner för standardkostnader. Varje kostnadsversion måste betecknas med en kostnadstyp för **standardkostnader** och måste tillåta att innehåll omfattar kostnadsdata.

**6. Förbered en befintlig -kund på att använda standardkostnader.** 

Kunder som vill ändra sina befintliga artiklar till lagermodellen Standardkostnad måste använda sidan **Konverteringar av standardkostnad**.


## <a name="related-articles"></a>Relaterade artiklar

[Standardkostnadskonvertering – översikt](standard-cost-conversion-overview.md)

### <a name="blogs"></a>Bloggar

#### <a name="community-blogs"></a>Community-bloggar

- [Så här ställer du in standardkostnader för direkt material i Ekonomi och drift](https://financefunction.tech/2018/06/07/how-to-set-up-standard-costs-for-direct-materials-in-dynamics-365-for-finance-and-operations)
- [Standardkostnader för direkt arbete i Ekonomi och drift](https://financefunction.tech/2018/07/16/standard-direct-labor-cost-in-dynamics-365-for-finance-and-operations)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
