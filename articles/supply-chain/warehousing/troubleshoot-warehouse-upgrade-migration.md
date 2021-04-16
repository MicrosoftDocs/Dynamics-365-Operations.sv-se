---
title: Felsöka uppgradering och migrering till avancerad distributionslagerhantering
description: I det här avsnittet beskrivs hur du åtgärdar vanliga problem som kan uppstå när du uppgraderar och migrerar till avancerad lagerhantering.
author: perlynne
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 953b828667a01157767c3ca79349fe972b0fbe9b
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5826405"
---
# <a name="troubleshoot-upgrade-and-migration-to-advanced-warehouse-management"></a><span data-ttu-id="ed60d-103">Felsöka uppgradering och migrering till avancerad distributionslagerhantering</span><span class="sxs-lookup"><span data-stu-id="ed60d-103">Troubleshoot upgrade and migration to advanced warehouse management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ed60d-104">I det här avsnittet beskrivs hur du åtgärdar vanliga problem som kan uppstå när du uppgraderar och migrerar till avancerad lagerhantering.</span><span class="sxs-lookup"><span data-stu-id="ed60d-104">This topic describes how to fix common issues that you might encounter while you upgrade and migrate to advanced warehouse management.</span></span>

## <a name="i-receive-the-following-error-message-javasecuritycertcertpathvalidatorexception-trust-anchor-for-certification-path-is-not-found"></a><span data-ttu-id="ed60d-105">Följande felmeddelande visas: "java.security.cert.certPathValidatorException: Förtroendeankare för certifieringsväg hittades inte".</span><span class="sxs-lookup"><span data-stu-id="ed60d-105">I receive the following error message: "java.security.cert.certPathValidatorException: Trust anchor for certification path is not found."</span></span>

### <a name="issue-description"></a><span data-ttu-id="ed60d-106">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="ed60d-106">Issue description</span></span>

<span data-ttu-id="ed60d-107">Det här felmeddelandet visas i mobilappen för distributionslagerhantering eftersom självsignerade certifikat inte är betrodda i Android 8+ i lokala miljöer.</span><span class="sxs-lookup"><span data-stu-id="ed60d-107">You receive this error message in the Warehouse Management mobile app, because self-signed certificates aren't trusted on Android 8+ in on-premises environments.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="ed60d-108">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="ed60d-108">Issue resolution</span></span>

<span data-ttu-id="ed60d-109">Använd en extern (offentlig) certifikatutfärdare (CA).</span><span class="sxs-lookup"><span data-stu-id="ed60d-109">Use an external (public) certifying authority (CA).</span></span> <span data-ttu-id="ed60d-110">En korrigeringsfil för det här problemet finns tillgänglig i version 1.9.0.0 av distributionslagerappen.</span><span class="sxs-lookup"><span data-stu-id="ed60d-110">A fix for this issue is available in version 1.9.0.0 of the warehouse app.</span></span> <span data-ttu-id="ed60d-111">Mer information om det här problemet och hur du åtgärdar det finns i [felsökning av anslutningsproblem för mobilappen för distributionslagerhantering](troubleshoot-warehouse-app-connection.md).</span><span class="sxs-lookup"><span data-stu-id="ed60d-111">For more information about this issue and how to fix it, see [Troubleshoot Warehouse Management mobile app connection issues](troubleshoot-warehouse-app-connection.md).</span></span>

## <a name="what-is-the-approved-process-for-moving-from-basic-warehousing-to-advanced-warehousing"></a><span data-ttu-id="ed60d-112">Vad är den godkända processen att flytta från grundläggande lagerstyrning till avancerad lagerstyrning?</span><span class="sxs-lookup"><span data-stu-id="ed60d-112">What is the approved process for moving from basic warehousing to advanced warehousing?</span></span>

### <a name="issue-description"></a><span data-ttu-id="ed60d-113">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="ed60d-113">Issue description</span></span>

<span data-ttu-id="ed60d-114">Du kör för närvarande under lager/lagerhantering och använder grundläggande lagerfunktion och du vill flytta till avancerad lager för att dra nytta av mobila enheter, påfyllnader och arbete.</span><span class="sxs-lookup"><span data-stu-id="ed60d-114">You're currently running under stock/inventory management and using basic stock functionality, and you want to move to advanced warehousing to take advantage of mobile devices, waves, and work.</span></span> <span data-ttu-id="ed60d-115">Du får emellertid problem när du försöker att göra denna flyttning.</span><span class="sxs-lookup"><span data-stu-id="ed60d-115">However, you're experiencing issues when you try to make this move.</span></span> <span data-ttu-id="ed60d-116">Du kan till exempel inte ändra produkter så att de använder lagringsdimensioner (webbplats, lagerställe och plats), eftersom produkterna har transaktioner gentemot dem.</span><span class="sxs-lookup"><span data-stu-id="ed60d-116">For example, you can't change your products so that they use storage dimensions (site, warehouse, and location), because the products have transactions against them.</span></span> <span data-ttu-id="ed60d-117">Därför måste du lära den godkända processen att flytta från grundläggande lagerstyrning till avancerad lagerstyrning.</span><span class="sxs-lookup"><span data-stu-id="ed60d-117">Therefore, you must learn the approved process for moving from basic warehousing to advanced warehousing.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="ed60d-118">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="ed60d-118">Issue resolution</span></span>

<span data-ttu-id="ed60d-119">Mer information om processen för att flytta från grundläggande lagerstyrning till avancerad lagring finns i följande blogginlägg och dokumentation:</span><span class="sxs-lookup"><span data-stu-id="ed60d-119">For more information about the process for moving from basic warehousing to advanced warehousing, see the following blog posts and documentation:</span></span>

- [<span data-ttu-id="ed60d-120">Aktivera lagerhanteringsprocessen för befintliga artiklar och lager</span><span class="sxs-lookup"><span data-stu-id="ed60d-120">Enable warehouse management process for existing items and warehouses</span></span>](https://cleverax.wordpress.com/2017/12/06/d365fo-enable-warehouse-management-process-for-existing-items-and-warehouses/)
- [<span data-ttu-id="ed60d-121">Migrering av Microsoft Dynamics AX WMS till nya R3 lagerställe- och transportfunktion</span><span class="sxs-lookup"><span data-stu-id="ed60d-121">Migration of Microsoft Dynamics AX WMS to new R3 warehouse and transportation functionality</span></span>](https://cloudblogs.microsoft.com/dynamics365/no-audience/2015/08/17/migration-of-microsoft-dynamics-ax-wms-to-new-r3-warehouse-and-transportation-functionality/)
- [<span data-ttu-id="ed60d-122">WMSI/WMS2 artikelmigrering</span><span class="sxs-lookup"><span data-stu-id="ed60d-122">WMSI/WMS2 item migration</span></span>](https://cloudblogs.microsoft.com/dynamics365/no-audience/2018/05/03/wmsiwms2-item-migration/)
- [<span data-ttu-id="ed60d-123">Uppgradera lagerstyrning från Microsoft Dynamics AX 2012 till Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="ed60d-123">Upgrade warehouse management from Microsoft Dynamics AX 2012 to Supply Chain Management</span></span>](https://docs.microsoft.com/dynamics365/supply-chain/warehousing/upgrade-migration-warehouse-management-processes)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]