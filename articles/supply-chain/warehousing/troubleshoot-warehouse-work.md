---
title: Felsöka distributionslagerarbete
description: I det här avsnittet beskrivs hur du åtgärdar vanliga problem som kan uppstå när du arbetar med lagerarbete i Microsoft Dynamics 365 Supply Chain Management.
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
ms.openlocfilehash: 08cc074fe851b952ebfc942ae3d1cb05240d3b91
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5837451"
---
# <a name="troubleshoot-warehouse-work"></a><span data-ttu-id="b3ff7-103">Felsöka distributionslagerarbete</span><span class="sxs-lookup"><span data-stu-id="b3ff7-103">Troubleshoot warehouse work</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b3ff7-104">I det här avsnittet beskrivs hur du åtgärdar vanliga problem som kan uppstå när du arbetar med lagerarbete i Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="b3ff7-104">This topic describes how to fix common issues that you might encounter while you work with warehouse work in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-cant-move-license-plates-that-have-serial-number-items-when-blank-issue-and-blank-receipt-are-allowed-on-the-tracking-dimension-group"></a><span data-ttu-id="b3ff7-105">Jag kan inte flytta ID-nummer som har serienummerartiklar när en tom utleverans och en tom inleverans är tillåten på spårningsdimensionsgruppen.</span><span class="sxs-lookup"><span data-stu-id="b3ff7-105">I can't move license plates that have serial number items when blank issue and blank receipt are allowed on the tracking dimension group.</span></span>

### <a name="issue-description"></a><span data-ttu-id="b3ff7-106">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="b3ff7-106">Issue description</span></span>

<span data-ttu-id="b3ff7-107">Du kan inte flytta ett ID-nummer genom att använda menyartikeln **Rörelse** om ett serienummer har inställningen *Tom utleverans tillåten* och *Tom inleverans tillåten* på spårningsdimensionsgruppen och om det finns flera ID-nummer på samma plats, varav några har serienummer och andra inte har dem.</span><span class="sxs-lookup"><span data-stu-id="b3ff7-107">You can't move a license plate by using a **Movement** menu item if the serial number has settings of *Blank issue allowed* and *Blank receipt allowed* on the tracking dimension group, and if there are multiple license plates in the same location, some of which have serial numbers and some of which don't have them.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="b3ff7-108">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="b3ff7-108">Issue resolution</span></span>

<span data-ttu-id="b3ff7-109">Det här problemet kommer att åtgärdas genom ändringar som distribueras i [KB-4571546](https://fix.lcs.dynamics.com/Issue/Details?kb=4571546&bugId=467880&dbType=3&qc=5b46d7faa9cc326cebfe9854cb30be8ea30b21ef33d3572c325fbb21202de687).</span><span class="sxs-lookup"><span data-stu-id="b3ff7-109">This issue will be fixed by changes that are deployed in [KB 4571546](https://fix.lcs.dynamics.com/Issue/Details?kb=4571546&bugId=467880&dbType=3&qc=5b46d7faa9cc326cebfe9854cb30be8ea30b21ef33d3572c325fbb21202de687).</span></span> <span data-ttu-id="b3ff7-110">Dessa ändringar gör fältet **serienummer** valfritt när en tom inleverans och en tom utleverans är tillåten.</span><span class="sxs-lookup"><span data-stu-id="b3ff7-110">Those changes will make the **Serial number** field optional when blank receipt and blank issue are allowed.</span></span>

## <a name="i-receive-the-following-error-message-in-the-warehouse-management-mobile-app-when-i-process-movements-the-inventory-owner-1-is-not-allowed-in-this-process"></a><span data-ttu-id="b3ff7-111">Jag får följande felmeddelande i modulen mobilappen för distributionslagerhantering när jag bearbetar transporter: "lagrets ägare %1 är inte tillåten i den här processen".</span><span class="sxs-lookup"><span data-stu-id="b3ff7-111">I receive the following error message in the Warehouse Management mobile app when I process movements: "The inventory owner %1 is not allowed in this process."</span></span>

### <a name="issue-description"></a><span data-ttu-id="b3ff7-112">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="b3ff7-112">Issue description</span></span>

<span data-ttu-id="b3ff7-113">Spårningsdimensionen **Ägare** spårningsdimension saknas när mobilappen för distributionslagerhantering används för att göra rörelser.</span><span class="sxs-lookup"><span data-stu-id="b3ff7-113">The **Owner** tracking dimension is missing when the Warehouse Management mobile app is used to make movements.</span></span> <span data-ttu-id="b3ff7-114">En vanlig lageröverföringsjournal från klienten Supply Chain Management visas som avsett arbete och kan endast bokföras om dimensionen **Ägare** fylls i.</span><span class="sxs-lookup"><span data-stu-id="b3ff7-114">A regular inventory transfer journal from the Supply Chain Management client appears to work as intended and can be posted only if the **Owner** dimension is filled in.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="b3ff7-115">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="b3ff7-115">Issue resolution</span></span>

<span data-ttu-id="b3ff7-116">Microsoft har utvärderat det här problemet och har fastställt att det är en funktionsbegränsning.</span><span class="sxs-lookup"><span data-stu-id="b3ff7-116">Microsoft has evaluated this issue and has determined that it's a feature limitation.</span></span> <span data-ttu-id="b3ff7-117">För närvarande stöder lagerhanteringsprocesserna endast lager som ägs av den juridiska personen.</span><span class="sxs-lookup"><span data-stu-id="b3ff7-117">Currently, warehouse management processes support only inventory that is owned by the legal entity.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]