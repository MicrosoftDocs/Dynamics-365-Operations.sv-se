---
title: Avbryt lagerarbete för undantagshantering
description: I det här avsnittet beskrivs funktionen Avbryt arbete som tillåter att jobbet för kontroll av lagerstyrning hanterar spärrat arbete.
author: omulvad
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSTroubIeshootingSeIfService, WHSTroubleshootingSelfService
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2019-10-1
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: daa8f0d19de75e6c126fe7a5fe312bca24c89bdc
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/16/2020
ms.locfileid: "4438030"
---
# <a name="cancel-warehouse-work-for-exception-handling"></a><span data-ttu-id="07c37-103">Avbryt lagerarbete för undantagshantering</span><span class="sxs-lookup"><span data-stu-id="07c37-103">Cancel warehouse work for exception handling</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="07c37-104">Med funktionen Avbryt arbete i Microsoft Dynamics 365 Supply Chain Management kan administratören avbryta ett specifikt lagerarbete som pågår, men som blockeras av systemet eller inte kan slutföras på grund av exceptionella omständigheter.</span><span class="sxs-lookup"><span data-stu-id="07c37-104">The Cancel work functionality in Microsoft Dynamics 365 Supply Chain Management lets the admin user cancel specific warehouse work that is currently in progress, but that is blocked by the system or can't be completed because of exceptional circumstances.</span></span> <span data-ttu-id="07c37-105">Den här funktionen är ett attraktivt och säkert alternativ till korrigeringsskript för SQL som korrigerar inkonsekventa data.</span><span class="sxs-lookup"><span data-stu-id="07c37-105">This functionality is an attractive and secure alternative to SQL corrective scripts that fix inconsistent data.</span></span> <span data-ttu-id="07c37-106">Dessa skript begärs emellertid vanligtvis av IT-proffs, men funktionen Avbryt arbete kan användas av användare i företaget som har administratörsbehörighet.</span><span class="sxs-lookup"><span data-stu-id="07c37-106">However, whereas these scripts are typically requested from IT professionals, the Cancel work functionality can be used by users in the company who have admin rights.</span></span>

<span data-ttu-id="07c37-107">Du kan komma åt funktionen Avbryt arbete på **Lagerstyrning** \> **Periodiska uppgifter** \> **Rensa \> Avbryt arbete**.</span><span class="sxs-lookup"><span data-stu-id="07c37-107">You can access the Cancel work functionality at **Warehouse management** \> **Periodic tasks** \> **Clean up \> Cancel work**.</span></span> <span data-ttu-id="07c37-108">I dialogruta **Avbryt arbete** för arbetet som ska avbrytas i dialogrutan Avbryt arbete och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="07c37-108">In the **Cancel work** dialog box, specify the work ID of the work to cancel, and then select **OK**.</span></span>

## <a name="warehouse-work-that-can-be-canceled"></a><span data-ttu-id="07c37-109">Lagerställe arbete som kan annulleras</span><span class="sxs-lookup"><span data-stu-id="07c37-109">Warehouse work that can be canceled</span></span>

<span data-ttu-id="07c37-110">Under lagerplocknings operationer kan en arbetare stöta på situationer där de har registrerat kvantiteter som har registrerats som plockade från en lagringsplats till sin plats, men de kan inte registrera placeringsoperationen.</span><span class="sxs-lookup"><span data-stu-id="07c37-110">During warehouse picking operations, a worker might encounter situations where they have registered quantities as picked from a storage location to their user location, but then they can't register the put operation.</span></span> <span data-ttu-id="07c37-111">Inkonsekventa lagerdata är ofta, men inte alltid, orsaken till varför arbetet blockeras.</span><span class="sxs-lookup"><span data-stu-id="07c37-111">Inconsistent warehouse data is often, but not always, the reason why work is blocked.</span></span>

<span data-ttu-id="07c37-112">Till skillnad från de vanliga avbrott som går att komma åt med hjälp av knappen **Avbryt** i arbetsrubriker, kräver inte funktionen Avbryt arbete att den sista slutförda arbetsraden är en arbetsrad av typen **plats**.</span><span class="sxs-lookup"><span data-stu-id="07c37-112">Unlike the regular Cancel functionality that can be accessed by using the **Cancel** button on the work header, the Cancel work functionality doesn't require that the last completed work line be a work line of the **put** type.</span></span> <span data-ttu-id="07c37-113">Med andra ord kan annulleringslogik köras även om artikelkvantiteten på en arbetsrad finns på en användarplats.</span><span class="sxs-lookup"><span data-stu-id="07c37-113">In other words, for the Cancel work functionality, cancellation logic can be run even if the item quantity on a work line is in a user location.</span></span>

> [!NOTE]
> <span data-ttu-id="07c37-114">För arbete som måste annulleras av funktionsskäl måste lageranvändarna fortsätta att använda den vanliga funktionen Avbryt på arbetssidan.</span><span class="sxs-lookup"><span data-stu-id="07c37-114">For work that must be canceled for operational reasons, warehouse users must continue to use the regular Cancel functionality on the work page.</span></span>

<span data-ttu-id="07c37-115">Endast arbete av typen **Försäljning**, **Överför leverans**, **Råmaterialhämtning** eller **Lagerpåfyllnad** kan annulleras genom att använda funktionen Avbryt arbete.</span><span class="sxs-lookup"><span data-stu-id="07c37-115">Only work of the **Sales**, **Transfer issue**, **Raw material picking**, or **Replenishment** type can be canceled by using the Cancel work functionality.</span></span> <span data-ttu-id="07c37-116">Annulleringslogik körs inte för plockningsarbete av fryst råmaterial eller arbete som kan avbrytas med funktionen Avbryt (se föregående notering).</span><span class="sxs-lookup"><span data-stu-id="07c37-116">Cancellation logic won't be run for frozen raw material picking work or work that can be canceled by using the regular Cancel functionality (see the preceding note).</span></span>

<span data-ttu-id="07c37-117">För att häva blockeringen av arbetet i systemet avbryts alla återstående arbetsrader och de lagerdata som är associerade med det arbets-ID som användaren anger avbryts.</span><span class="sxs-lookup"><span data-stu-id="07c37-117">To unblock the work, the system cancels any remaining work lines and fixes the warehouse data that is associated with the work ID that the user specified.</span></span> <span data-ttu-id="07c37-118">Alla vanliga lagerhanteringsoperationer som rör berörd artikelkvantitet kan sedan återupptas.</span><span class="sxs-lookup"><span data-stu-id="07c37-118">Any regular warehouse-handling operations that involve the affected item quantity can then resume.</span></span>

<span data-ttu-id="07c37-119">Om du vill placera den berörda artikeln på en viss plats efter att arbetet avbrutits måste användaren använda en lagerrörelse eller en kvantitetjusteringsåtgärd på en mobil enhet.</span><span class="sxs-lookup"><span data-stu-id="07c37-119">To put the affected item in a specific location after the work is canceled, the user must use an inventory movement or quantity adjustment operation on a mobile device.</span></span>
