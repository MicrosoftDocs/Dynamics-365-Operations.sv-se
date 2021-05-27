---
title: Ställa in en e-handelsutvecklingsmiljö för felsökning mot en virtuell dator för nivå 1 Retail Server
description: Det här ämnet förklarar hur du ställer in en e-handelsutvecklingsmiljö för felsökning mot en virtuell dator för nivå 1 Retail Server (VM).
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 38a616c418c3b32490c9adaf69a69af0d47d3478
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6019456"
---
# <a name="set-up-an-e-commerce-development-environment-to-debug-against-a-tier-1-retail-server-virtual-machine"></a>Ställa in en e-handelsutvecklingsmiljö för felsökning mot en virtuell dator för nivå 1 Retail Server

[!include [banner](../../includes/banner.md)]

Det här ämnet förklarar hur du ställer in en e-handelsutvecklingsmiljö för felsökning mot en virtuell dator för nivå 1 Retail Server (VM).

## <a name="description"></a>beskrivning

Microsoft Dynamics 365 Commerce nivå 1-miljöer distribueras normalt för Commerce Runtime (CRT) och utökning av kassa (POS). De är fristående miljöer. På grund av programvaran som en tjänst (SaaS) karaktär av arkitekturen, omfattar de inte komponenter för e-handel.

I vissa scenarier kanske du vill testa anrop till tillägg i en nivå 1-miljö, så att du kan felsöka tillägg från e-handelskomponenter. För allmänna instruktioner, se [Felsöka mot en nivå 1 Commerce utvecklingsmiljö](../e-commerce-extensibility/debug-tier-1.md).

När du felsöker mot en nivå 1-miljö, eftersom webbplatsen nu anropar en annan Retail Server, kan det leda till olika fel som hör till säkerhetspolicyn för innehåll.

I bilden nedan visas ett exempel på ett fel som kan inträffa när en variant väljs på en produktinformationssida.

![Fel när en variant väljs på en produktinformationssida](media/unhandled-rejection-error.jpg)

I följande bild visas ett exempel på ett liknande fel i en webbläsares felsökningsverktyg (F12 utvecklarverktyg). Felmeddelandet tar upp brott mot säkerhetspolicyn för innehåll.

![Fel i felsökningsverktyg](media/debugger-tools-error.JPG)

## <a name="resolution"></a>Upplösning

### <a name="disable-the-content-security-policy-for-the-site-in-commerce-site-builder"></a>Inaktivera säkerhetspolicyn för innehåll för webbplatsen i Commerce-webbplatsbyggaren

1. Välj den webbplats som du arbetar på.
1. Välj **inställningar** och välj sedan **tillägg**.
1. På fliken **Innehållssäkerhetspolicy**, välj **Inaktivera säkerhetspolicy för innehåll**.
1. Välj **Spara och publicera**.

> [!NOTE]
> In inloggning mellan företag till kund (B2C) fungerar inte i en lokal utvecklingsmiljö. Du kan dock använda gästutcheckningar eller skapa sidutdata för att simulera en användarindata vid behov.

## <a name="additional-resources"></a>Ytterligare resurser

[Kom i gång med utbyggnadsutveckling av näthandel](../e-commerce-extensibility/sdk-getting-started.md)

[Hantera säkerhetspolicy för innehåll (CSP) på e-handelsplats](../manage-csp.md)
