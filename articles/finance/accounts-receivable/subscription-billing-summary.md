---
title: Översikt över prenumerationsfakturering
description: I det här avsnittet beskrivs hur du ställer in prenumerationsfakturering i Microsoft Dynamics 365 Finance.
author: JodiChristiansen
ms.date: 02/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustPosting, CustVendExternalItem
audience: Application User
ms.reviewer: twheeloc
ms.custom: 24651
ms.assetid: cb82245e-8c02-429c-b36e-8db0e3e6f7e5
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2022-02-09
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: 2796e25ec783941de381fb5ae96145eeba870bde
ms.sourcegitcommit: c0f7ee7f8837fec881e97b2a3f12e7f63cf96882
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/22/2022
ms.locfileid: "8462481"
---
# <a name="subscription-billing-overview"></a>Översikt över prenumerationsfakturering

[!include [banner](../includes/banner.md)]

Med prenumerationsfakturering kan organisationer hantera affärsmöjligheter för abonnemangsintäkter och återkommande fakturering via faktureringsscheman. Komplexa prissättnings- och faktureringsmodeller och intäktsallokering hanteras enkelt och faktureras och identifieras på radnivå. Multi-element intäktsallokering möjliggör allokering av inkomster för att följa International Accounting Standards (International Financial Reporting Standard 15 \[IFRS 15\]) och allmänt accepterade redovisningsprinciper (US GAAP) standarder (Accounting Standards Codification Topic 606 \[ASC 606\]).

Lösningen har tre moduler som kan användas oberoende av varandra. Alternativt kan alla tre moduler användas tillsammans.

- **Återkommande fakturering av kontrakt** – Med den här modulen kan återkommande fakturering och prishantering ge kontroll över prissättningar och faktureringsparametrar, kontrakt och konsoliderad fakturering.
- **Intäkts- och kostnadsuppskjutningar** – Denna modul eliminerar manuella processer och beroende av externa system genom att hantera intäkter och möjliggöra realtidsinsikter i månatliga återkommande intäkter.
- **Multi-element intäktsallokering med flera element** – Den här modulen hjälper till med intäktsefterlevnad genom att hantera prissättning och intäktsallokering för flera artiklar.

Abonnemangsfakturering aktiveras via **funktionshanteringen**. Den kan emellertid inte användas med funktionen **intäktsredovisning**. Därför måste du inaktivera den funktionen innan du aktiverar prenumerationsfakturering.

1. I arbetsytan **funktionshantering** på fliken **Alla** ange **Intäktsredovisning** i filtret och välj sedan funktionsnamnet som filter.
2. Markera funktionen **Intäktsredovisning** och välj sedan **Inaktivera**.
3. I **funktionsnamn** ange **prenumerationsfakturering** och välj sedan modulfilter.
4. Välj fakturering **prenumerationsfakturering** och aktivera **aktivera**.
5. Välj en av de tre modulerna i den föregående listan och välj sedan **Aktivera**. Upprepa detta steg för var och en av de andra två modulerna.

    > [!IMPORTANT]
    > Funktionen **prenumerationsfakturering** måste vara aktiverad innan du kan aktivera någon av de tre modulerna.
