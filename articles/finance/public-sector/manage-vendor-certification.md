---
title: Underhålla leverantörscertifieringar
description: I denna artikel beskrivs vilka steg leverantörer kan vidta när de underhåller sina certifieringar med hjälp av arbetsytan för leverantörssamarbeten.
author: v-kiarnd
ms.date: 04/27/2021
ms.topic: article
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2021-02-09
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 37990292748c363f44d306bda0263dd117808eb1
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8891449"
---
# <a name="maintain-vendor-certification"></a>Underhålla leverantörscertifieringar

[!include [banner](../includes/banner.md)]

I denna artikel beskrivs vilka steg som dina leverantörer kan vidta när de underhåller sina certifieringar med hjälp av **arbetstytan för leverantörssamarbeten**. Exempel på certifieringar kan till exempel vara ett WBE (Woman Business Enterprise) eller ett företag med certifieringen Energy and Environment Design (LEED). Leverantörer måste ange certifieringsinformation i arbetsytan **Leverantörsinformation**. Därifrån väljer leverantörerna **Mer information** och sedan **Certifieringar**.

## <a name="turn-on-the-vendor-certification-feature"></a>Aktivera leverantörsintygsfunktionen

Innan du kan använda den här funktionen den aktiveras i ditt system. Administratörer kan använda sidan [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den om det behövs. I arbetsytan **utgiftshantering** anges den här funktionen på följande sätt:

- **Modul** - *Leverantörsreskontra*
- **Funktionsnamn** - *Aktivera certifieringshantering för leverantörssamarbete*

## <a name="add-a-new-certification"></a>Lägga till en ny certifiering

Lägg till ett nytt certifikat genom att välja knappen **Lägg** som finns ovanför rutnätet **Certifiering** i arbetsytan **Leverantörsinformation**. Ange följande information:

- Intygsnummer
- Intygstyp
- Intygsutfärdare
- Intygsdatum
- Skuldbelopp, om tillämpligt
- Gäller från
- Utgångsdatum
- Kommentarer (valfritt)

Om det finns dokument som hör till den specifika certifieringen kan du koppla dessa genom att välja knappen **Dokument**.

Certifieringar som anges av dina leverantörer på den här sidan kommer att tilldelas en källa tillhörande "Leverantör". Du kan ange intygsinformation för leverantörens räkning under leverantörsbankkonton. Informationen visas här och källan visas som **Kund**.

Leverantörer kan redigera eller ta bort sina certifieringar efter behov.

## <a name="vendor-collaboration-generated-certification-records"></a>Certifieringsposter som genereras genom leverantörssamarbete

När certifieringsinformationen har lagts till av en leverantör visas informationen på sidan **Certifieringar som genereras genom leverantörssamarbete**. Öppna sidan genom att gå till **Leverantörsreskontra > Förfrågningar > Leverantörsrapporter > Certifieringar som genereras genom leverantörssamarbete**. Som standard visas alla nya eller ändrade certifieringsposter. En leverantörsreskontraansvarig kan granska ändringarna och validera informationen via sin bekräftelseprocess för validering. När informationen har bekräftats kan certifieringsposten som visas på sidan väljas och markeras som granskad. Om du markerar posten som granskad tas den bort från standardlistan.

Alla certifieringsändringar visas på sidan **Certifieringar som genereras genom leverantörssamarbete**. Om en ändring inte visas på sidan kan du visa den genom att justera filtren för leverantörskontot, giltighetsdatumintervallet eller välja om du vill ta med information för certifieringsändringar som har granskats.

