---
title: Inställning av dubbelriktad skrivning från Lifecycle Services
description: I det här avsnittet beskrivs hur du ställer in en dubbelriktad anslutning från Microsoft Dynamics Lifecycle Services (LCS).
author: RamaKrishnamoorthy
ms.date: 01/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: e51b4ef1e309e5f89dc82a3776b88c505dc6593d
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5748551"
---
# <a name="dual-write-setup-from-lifecycle-services"></a>Inställning av dubbelriktad skrivning från Lifecycle Services

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

I det här avsnittet beskrivs hur du ställer in en dubbelriktad anslutning i en ny Finance and Operations-miljö och en ny Dataverse-miljö från Microsoft Dynamics Lifecycle Services (LCS).

## <a name="prerequisites"></a>Förutsättningar

Du måste vara administratör för att kunna konfigurera en anslutning med dubbelriktad anslutning.

+ Du måste ha åtkomst till innehavare.
+ Du måste vara administratör i både Finance and Operations-miljöer och Dataverse-miljöer.

## <a name="set-up-a-dual-write-connection"></a>Konfigurera en dubbelriktad anslutning

Följ dessa steg för att konfigurera dubbelriktad anslutning.

1. I LCS till ditt projekt.
2. Välj **konfigurera** om du vill distribuera en ny miljö.
3. Välj version. 
4. Välj topologi. Om det bara finns en tillgänglig topologi väljs den automatiskt.
5. Slutför de första stegen i guiden **distributionsinställningar**.
6. På fliken **Dataverse** följ stegen:

    - Om en Dataverse-miljö redan har etablerats för din klientorganisation kan du välja den.

        1. Ange alternativet **Konfigurera Dataverse** till **Ja**.
        2. I kolumnen **Tillgängliga miljöer** välj miljön som ska integreras med dina Finance and Operations data. Listan innehåller alla miljöer där du har administratörsbehörighet.
        3. Markera kryssrutan **acceptera** för att ange att du godkänner villkoren.

        ![Fliken Dataverse när en Dataverse-miljö redan har etablerats för din klientorganisation](../dual-write/media/lcs_setup_1.png)

    - Om din klientorganisation inte redan har en Dataverse-miljö, kommer en ny miljö att etableras.

        1. Ange alternativet **Konfigurera Dataverse** till **Ja**.
        2. Ange ett namn på Dataverse-miljön.
        3. Välj regionen som miljön ska distribueras till.
        4. Välj standardspråk och valuta för miljön.

            > [!NOTE]
            > Du kan inte ändra språk och valuta senare.

        5. Markera kryssrutan **acceptera** för att ange att du godkänner villkoren.

        ![Dataverse fliken när din klientorganisation inte redan har Dataverse-miljö](../dual-write/media/lcs_setup_2.png)

7. Slutför de kvarstående stegen i guiden **distributionsinställningar**.
8. När miljön har statusen **distribuerad** ska du öppna sidan miljöinformation. I avsnittet **Power Platform-integration** visas namnen på Finance and Operations-miljön och Dataverse-miljön som är länkade.

    ![Power Platform-integrationsavsnitt](../dual-write/media/lcs_setup_3.png)

9. En administratör för Finance and Operations-miljön måste logga in på LCS och välja **länka till CDS-skivor för appar** för att slutföra länken. På sidan miljöinformation visas kontaktinformationen för administratören.

    När länken är slutförd uppdateras status till **Miljölänkning har slutförts**.

10. Öppna arbetsytan **Dataintegration** i Finance and Operations-miljön och kontrollera vilka mallar som är tillgängliga, välj **Länk till CDS för appar**.

    ![Knappen länk till CDS för appar i avsnittet Power Platform-integration](../dual-write/media/lcs_setup_4.png)

> [!NOTE]
> Du kan inte avlänka miljöer med hjälp av LCS. Om du vill ta bort länken för en miljö, öppna arbetsytan **Dataintegration** i Finance and Operations-miljön och välj sen **Ta bort länk**.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]