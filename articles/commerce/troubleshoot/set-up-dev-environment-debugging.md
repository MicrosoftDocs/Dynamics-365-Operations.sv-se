---
title: Ställa in en näthandelsutvecklingsmiljö för felsökning mot en virtuell dator för nivå 1 Retail Server
description: Denna artikel förklarar hur du konfigurerar en näthandelsutvecklingsmiljö för felsökning mot en virtuell dator för nivå 1 Retail Server (VM).
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.custom: ''
ms.assetid: ''
ms.search.industry: Retail
ms.openlocfilehash: 64e03c742f7095e2e485f32ad534f2a755ddd062
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9277890"
---
# <a name="set-up-an-e-commerce-development-environment-to-debug-against-a-tier-1-retail-server-virtual-machine"></a>Ställa in en näthandelsutvecklingsmiljö för felsökning mot en virtuell dator för nivå 1 Retail Server

[!include [banner](../../includes/banner.md)]

Denna artikel förklarar hur du konfigurerar en näthandelsutvecklingsmiljö för felsökning mot en virtuell dator för nivå 1 Retail Server (VM).

## <a name="description"></a>beskrivning

Microsoft Dynamics 365 Commerce nivå 1-miljöer distribueras normalt för Commerce Runtime (CRT) och utökning av kassa (POS). De är fristående miljöer. På grund av programvaran som en tjänst (SaaS) karaktär av arkitekturen, omfattar de inte komponenter för näthandel.

I vissa scenarier kanske du vill testa anrop till tillägg i en nivå 1-miljö, så att du kan felsöka tillägg från näthandelskomponenter. För allmänna instruktioner, se [Felsöka mot en nivå 1 Commerce utvecklingsmiljö](../e-commerce-extensibility/debug-tier-1.md).

När du felsöker mot en nivå 1-miljö, eftersom webbplatsen nu anropar en annan Retail Server, kan det leda till olika fel som hör till säkerhetspolicyn för innehåll.

I bilden nedan visas ett exempel på ett fel som kan inträffa när en variant väljs på en produktinformationssida.

![Fel när en variant väljs på en produktinformationssida.](media/unhandled-rejection-error.jpg)

I följande bild visas ett exempel på ett liknande fel i en webbläsares felsökningsverktyg (F12 utvecklarverktyg). Felmeddelandet tar upp brott mot säkerhetspolicyn för innehåll.

![Fel i felsökningsverktyg.](media/debugger-tools-error.JPG)

## <a name="resolution"></a>Lösning

### <a name="disable-the-content-security-policy-for-the-site-in-commerce-site-builder"></a>Inaktivera säkerhetspolicyn för innehåll för webbplatsen i Commerce-webbplatsbyggaren

1. Välj den webbplats som du arbetar på.
1. Välj **inställningar** och välj sedan **tillägg**.
1. På fliken **Innehållssäkerhetspolicy**, välj **Inaktivera säkerhetspolicy för innehåll**.
1. Välj **Spara och publicera**.

> [!NOTE]
> In inloggning mellan företag till kund (B2C) fungerar inte i en lokal utvecklingsmiljö. Du kan dock använda gästkassor eller skapa sidutdata för att simulera en användarindata vid behov.

## <a name="additional-resources"></a>Ytterligare resurser

[Kom i gång med utbyggnadsutveckling av näthandel](../e-commerce-extensibility/sdk-getting-started.md)

[Hantera säkerhetspolicy för innehåll (CSP) på näthandelsplats](../manage-csp.md)
