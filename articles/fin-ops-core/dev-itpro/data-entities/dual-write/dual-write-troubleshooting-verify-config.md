---
title: Kontrollera att dubbelriktad skrivning i Finance and Operations-appar och Dataverse
description: I det här avsnittet beskrivs hur du kan avgöra om dubbelriktad skrivning är konfigurerad i Finance and Operations-appar och i Dataverse.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
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
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 0a1da32713f3d4d19b4d343c5b67b416a6c4ffbb
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5566775"
---
# <a name="verify-dual-write-configuration-in-finance-and-operations-apps-and-dataverse"></a><span data-ttu-id="1bb9d-103">Kontrollera att dubbelriktad skrivning i Finance and Operations-appar och Dataverse</span><span class="sxs-lookup"><span data-stu-id="1bb9d-103">Verify dual-write configuration in Finance and Operations apps and Dataverse</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



<span data-ttu-id="1bb9d-104">Det här avsnittet innehåller felsökningsinformation för integrering av dubbelriktad skrivning mellan Finance and Operations-appar och Dataverse.</span><span class="sxs-lookup"><span data-stu-id="1bb9d-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Dataverse.</span></span> <span data-ttu-id="1bb9d-105">Det beskriver särskilt hur du kan avgöra om dubbelriktad skrivning är konfigurerad i Finance and Operations-appar och i Dataverse.</span><span class="sxs-lookup"><span data-stu-id="1bb9d-105">Specifically, it explains how you can determine whether dual-write is configured in Finance and Operations apps and in Dataverse.</span></span>

## <a name="verify-that-dual-write-is-configured-in-a-finance-and-operations-app"></a><span data-ttu-id="1bb9d-106">Kontrollera att dubbelriktad skrivning är konfigurerad i en Finance and Operations-app</span><span class="sxs-lookup"><span data-stu-id="1bb9d-106">Verify that dual-write is configured in a Finance and Operations app</span></span>

<span data-ttu-id="1bb9d-107">För att avgöra om de fel som visas när du försöker spara rader för uppdatering kommer från dubbelriktad skrivning, ska du först kontrollera att dubbelriktad skrivning är konfigurerad.</span><span class="sxs-lookup"><span data-stu-id="1bb9d-107">To determine whether the errors that you see when you try to save rows for update come from dual-write, first verify that dual-write is configured.</span></span>

+ <span data-ttu-id="1bb9d-108">Om du har administratörsbehörighet i Finance and Operations-appen, gå till **Arbetsytor \> Datahantering** och välj panelen **dubbelriktad skrivning**.</span><span class="sxs-lookup"><span data-stu-id="1bb9d-108">If you have admin privileges in the Finance and Operations app, go to **Workspaces \> Data management**, and select the **Dual-write** tile.</span></span> <span data-ttu-id="1bb9d-109">Om information om de länkade miljöerna och listan över tabellmappningar som körs visas, konfigureras dubbelriktad skrivning.</span><span class="sxs-lookup"><span data-stu-id="1bb9d-109">If the details of the linked environments and the list of table maps that are running are shown, dual-write is configured.</span></span>

    ![Verifiera Finance and Operations-appanslutningen när du har administratörsbehörighet](media/verify_fin_ops_1.png)

+ <span data-ttu-id="1bb9d-111">Om du inte har administratörsbehörighet visas ett felmeddelande *Det går inte att skriva data till entitet \<entity name\>*.</span><span class="sxs-lookup"><span data-stu-id="1bb9d-111">If you don't have admin privileges, you will receive an error message, *Unable to write data to entity \<entity name\>*.</span></span> <span data-ttu-id="1bb9d-112">I exemplet i följande bild kan du inte skapa en kundrad i Finance and Operations-appen eftersom dubbelriktad skrivning är konfigurerad men referensdata för kundgrupp och betalningsvillkor finns inte i Dataverse.</span><span class="sxs-lookup"><span data-stu-id="1bb9d-112">In the example in the following illustration, you can't create a customer row in the Finance and Operations app, because dual-write is configured, but the customer group and payment terms reference data don't exist in Dataverse.</span></span>

    ![Verifiera Finance and Operations-appanslutningen när du inte har administratörsbehörighet](media/verify_fin_ops_2.png)

<span data-ttu-id="1bb9d-114">Information om hur du åtgärdar problem när du skapar data i Finance and Operations-appar finns i [Felsöka problem med realtidssynkronisering](dual-write-troubleshooting-live-sync.md).</span><span class="sxs-lookup"><span data-stu-id="1bb9d-114">For information about how to fix issues when you create data in Finance and Operations apps, see [Troubleshoot live synchronization issues](dual-write-troubleshooting-live-sync.md).</span></span>

## <a name="verify-that-dual-write-is-configured-in-dataverse"></a><span data-ttu-id="1bb9d-115">Kontrollera att dubbelriktad skrivning är konfigurerad i Dataverse</span><span class="sxs-lookup"><span data-stu-id="1bb9d-115">Verify that dual-write is configured in Dataverse</span></span>

<span data-ttu-id="1bb9d-116">När du skapar data, om du ser kolumnen **Företag** på sidor i Dataverse, är dubbelriktad skrivning konfigurerad.</span><span class="sxs-lookup"><span data-stu-id="1bb9d-116">When you create data, if you see the **Company** column on pages in Dataverse, dual-write is configured.</span></span>

![Verifierar Dataverse-anslutningen](media/verify_cds.png)

<span data-ttu-id="1bb9d-118">Information om hur du åtgärdar problem när du skapar data i Dataverse finns i [Felsöka problem med realtidssynkronisering](dual-write-troubleshooting-live-sync.md).</span><span class="sxs-lookup"><span data-stu-id="1bb9d-118">For information about how to fix issues when you create data in Dataverse, see [Troubleshoot live synchronization issues](dual-write-troubleshooting-live-sync.md).</span></span>

<span data-ttu-id="1bb9d-119">Information om hur du visar felinformation om du stöter på några fel medan du skapar data i Dataverse finns i [Aktivera och visa spårningslogg för plugin-program i Dataverse för att visa felinformation](dual-write-troubleshooting.md#enable-view-trace).</span><span class="sxs-lookup"><span data-stu-id="1bb9d-119">For information about how to view error details if you encounter any errors while you create data in Dataverse, see [Enable and view the plug-in trace log in Dataverse to view error details](dual-write-troubleshooting.md#enable-view-trace).</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]