---
title: Kontrollera att dubbelriktad skrivning är konfigurerad i Finance and Operations-appar och Common Data Service
description: I det här avsnittet beskrivs hur du kan avgöra om dubbelriktad skrivning är konfigurerad i Finance and Operations-appar och i Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: 2ddac76871a3ac574a1edcb5446be6c64e5e4682
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "3997240"
---
# <a name="verify-that-dual-write-is-configured-in-finance-and-operations-apps-and-common-data-service"></a><span data-ttu-id="227fe-103">Kontrollera att dubbelriktad skrivning är konfigurerad i Finance and Operations-appar och Common Data Service</span><span class="sxs-lookup"><span data-stu-id="227fe-103">Verify that dual-write is configured in Finance and Operations apps and Common Data Service</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="227fe-104">Det här avsnittet innehåller felsökningsinformation för integrering av dubbelriktad skrivning mellan Finance and Operations-appar och Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="227fe-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="227fe-105">Det beskriver särskilt hur du kan avgöra om dubbelriktad skrivning är konfigurerad i Finance and Operations-appar och i Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="227fe-105">Specifically, it explains how you can determine whether dual-write is configured in Finance and Operations apps and in Common Data Service.</span></span>

## <a name="verify-that-dual-write-is-configured-in-a-finance-and-operations-app"></a><span data-ttu-id="227fe-106">Kontrollera att dubbelriktad skrivning är konfigurerad i en Finance and Operations-app</span><span class="sxs-lookup"><span data-stu-id="227fe-106">Verify that dual-write is configured in a Finance and Operations app</span></span>

<span data-ttu-id="227fe-107">För att avgöra om de fel som visas när du försöker spara poster för uppdatering kommer från dubbelriktad skrivning, kontrollera först att dubbelriktad skrivning är konfigurerad.</span><span class="sxs-lookup"><span data-stu-id="227fe-107">To determine whether the errors that you see when you try to save records for update come from dual-write, first verify that dual-write is configured.</span></span>

+ <span data-ttu-id="227fe-108">Om du har administratörsbehörighet i Finance and Operations-appen, gå till **Arbetsytor \> Datahantering** och välj panelen **dubbelriktad skrivning**.</span><span class="sxs-lookup"><span data-stu-id="227fe-108">If you have admin privileges in the Finance and Operations app, go to **Workspaces \> Data management** , and select the **Dual-write** tile.</span></span> <span data-ttu-id="227fe-109">Om information om de länkade miljöerna och listan över entitetsmappningar som körs visas, konfigureras dubbelriktad skrivning.</span><span class="sxs-lookup"><span data-stu-id="227fe-109">If the details of the linked environments and the list of entity maps that are running are shown, dual-write is configured.</span></span>

    ![Verifiera Finance and Operations-appanslutningen när du har administratörsbehörighet](media/verify_fin_ops_1.png)

+ <span data-ttu-id="227fe-111">Om du inte har administratörsbehörighet visas ett felmeddelande *Det går inte att skriva data till entitet \<entity name\>*.</span><span class="sxs-lookup"><span data-stu-id="227fe-111">If you don't have admin privileges, you will receive an error message, *Unable to write data to entity \<entity name\>*.</span></span> <span data-ttu-id="227fe-112">I exemplet i följande bild kan du inte skapa en kundpost i Finance and Operations-appen eftersom dubbelriktad skrivning är konfigurerad men referensdata för kundgrupp och betalningsvillkor finns inte i Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="227fe-112">In the example in the following illustration, you can't create a customer record in the Finance and Operations app, because dual-write is configured, but the customer group and payment terms reference data don't exist in Common Data Service.</span></span>

    ![Verifiera Finance and Operations-appanslutningen när du inte har administratörsbehörighet](media/verify_fin_ops_2.png)

<span data-ttu-id="227fe-114">Information om hur du åtgärdar problem när du skapar data i Finance and Operations-appar finns i [Felsöka problem med realtidssynkronisering](dual-write-troubleshooting-live-sync.md).</span><span class="sxs-lookup"><span data-stu-id="227fe-114">For information about how to fix issues when you create data in Finance and Operations apps, see [Troubleshoot live synchronization issues](dual-write-troubleshooting-live-sync.md).</span></span>

## <a name="verify-that-dual-write-is-configured-in-common-data-service"></a><span data-ttu-id="227fe-115">Kontrollera att dubbelriktad skrivning är konfigurerad i Common Data Service</span><span class="sxs-lookup"><span data-stu-id="227fe-115">Verify that dual-write is configured in Common Data Service</span></span>

<span data-ttu-id="227fe-116">När du skapar data, om du ser fältet **Företag** på sidor i Common Data Service, är dubbelriktad skrivning konfigurerad.</span><span class="sxs-lookup"><span data-stu-id="227fe-116">When you create data, if you see the **Company** field on pages in Common Data Service, dual-write is configured.</span></span>

![Verifierar Common Data Service-anslutningen](media/verify_cds.png)

<span data-ttu-id="227fe-118">Information om hur du åtgärdar problem när du skapar data i Common Data Service finns i [Felsöka problem med realtidssynkronisering](dual-write-troubleshooting-live-sync.md).</span><span class="sxs-lookup"><span data-stu-id="227fe-118">For information about how to fix issues when you create data in Common Data Service, see [Troubleshoot live synchronization issues](dual-write-troubleshooting-live-sync.md).</span></span>

<span data-ttu-id="227fe-119">Information om hur du visar felinformation om du stöter på några fel medan du skapar data i Common Data Service finns i [Aktivera och visa spårningslogg för plugin-program i Common Data Service för att visa felinformation](dual-write-troubleshooting.md#enable-and-view-the-plug-in-trace-log-in-common-data-service-to-view-error-details).</span><span class="sxs-lookup"><span data-stu-id="227fe-119">For information about how to view error details if you encounter any errors while you create data in Common Data Service, see [Enable and view the plug-in trace log in Common Data Service to view error details](dual-write-troubleshooting.md#enable-and-view-the-plug-in-trace-log-in-common-data-service-to-view-error-details).</span></span>
