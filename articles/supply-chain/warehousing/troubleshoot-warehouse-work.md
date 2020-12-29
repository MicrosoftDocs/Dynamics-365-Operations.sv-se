---
title: Felsöka distributionslagerarbete
description: I det här avsnittet beskrivs hur du åtgärdar vanliga problem som kan uppstå när du arbetar med lagerarbete i Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: a00ae517ff583e4231099d8e9f5d5b5a696cf7f7
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/25/2020
ms.locfileid: "4645803"
---
# <a name="troubleshoot-warehouse-work"></a><span data-ttu-id="af5c1-103">Felsöka distributionslagerarbete</span><span class="sxs-lookup"><span data-stu-id="af5c1-103">Troubleshoot warehouse work</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="af5c1-104">I det här avsnittet beskrivs hur du åtgärdar vanliga problem som kan uppstå när du arbetar med lagerarbete i Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="af5c1-104">This topic describes how to fix common issues that you might encounter while you work with warehouse work in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-cant-move-license-plates-that-have-serial-number-items-when-blank-issue-and-blank-receipt-are-allowed-on-the-tracking-dimension-group"></a><span data-ttu-id="af5c1-105">Jag kan inte flytta ID-nummer som har serienummerartiklar när en tom utleverans och en tom inleverans är tillåten på spårningsdimensionsgruppen.</span><span class="sxs-lookup"><span data-stu-id="af5c1-105">I can't move license plates that have serial number items when blank issue and blank receipt are allowed on the tracking dimension group.</span></span>

### <a name="issue-description"></a><span data-ttu-id="af5c1-106">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="af5c1-106">Issue description</span></span>

<span data-ttu-id="af5c1-107">Du kan inte flytta ett ID-nummer genom att använda menyartikeln **Rörelse** om ett serienummer har inställningen *Tom utleverans tillåten* och *Tom inleverans tillåten* på spårningsdimensionsgruppen och om det finns flera ID-nummer på samma plats, varav några har serienummer och andra inte har dem.</span><span class="sxs-lookup"><span data-stu-id="af5c1-107">You can't move a license plate by using a **Movement** menu item if the serial number has settings of *Blank issue allowed* and *Blank receipt allowed* on the tracking dimension group, and if there are multiple license plates in the same location, some of which have serial numbers and some of which don't have them.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="af5c1-108">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="af5c1-108">Issue resolution</span></span>

<span data-ttu-id="af5c1-109">Det här problemet kommer att åtgärdas genom ändringar som distribueras i [KB-4571546](https://fix.lcs.dynamics.com/Issue/Details?kb=4571546&bugId=467880&dbType=3&qc=5b46d7faa9cc326cebfe9854cb30be8ea30b21ef33d3572c325fbb21202de687).</span><span class="sxs-lookup"><span data-stu-id="af5c1-109">This issue will be fixed by changes that are deployed in [KB 4571546](https://fix.lcs.dynamics.com/Issue/Details?kb=4571546&bugId=467880&dbType=3&qc=5b46d7faa9cc326cebfe9854cb30be8ea30b21ef33d3572c325fbb21202de687).</span></span> <span data-ttu-id="af5c1-110">Dessa ändringar gör fältet **serienummer** valfritt när en tom inleverans och en tom utleverans är tillåten.</span><span class="sxs-lookup"><span data-stu-id="af5c1-110">Those changes will make the **Serial number** field optional when blank receipt and blank issue are allowed.</span></span>

## <a name="i-receive-the-following-error-message-in-the-warehouse-app-when-i-process-movements-the-inventory-owner-1-is-not-allowed-in-this-process"></a><span data-ttu-id="af5c1-111">Jag får följande felmeddelande i modulen lagerställe när jag bearbetar transporter: "lagrets ägare %1 är inte tillåten i den här processen".</span><span class="sxs-lookup"><span data-stu-id="af5c1-111">I receive the following error message in the warehouse app when I process movements: "The inventory owner %1 is not allowed in this process."</span></span>

### <a name="issue-description"></a><span data-ttu-id="af5c1-112">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="af5c1-112">Issue description</span></span>

<span data-ttu-id="af5c1-113">Spårningsdimensionen **Ägare** spårningsdimension saknas när distributionslagerappen används för att göra rörelser.</span><span class="sxs-lookup"><span data-stu-id="af5c1-113">The **Owner** tracking dimension is missing when the warehouse app is used to make movements.</span></span> <span data-ttu-id="af5c1-114">En vanlig lageröverföringsjournal från klienten Supply Chain Management visas som avsett arbete och kan endast bokföras om dimensionen **Ägare** fylls i.</span><span class="sxs-lookup"><span data-stu-id="af5c1-114">A regular inventory transfer journal from the Supply Chain Management client appears to work as intended and can be posted only if the **Owner** dimension is filled in.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="af5c1-115">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="af5c1-115">Issue resolution</span></span>

<span data-ttu-id="af5c1-116">Microsoft har utvärderat det här problemet och har fastställt att det är en funktionsbegränsning.</span><span class="sxs-lookup"><span data-stu-id="af5c1-116">Microsoft has evaluated this issue and has determined that it's a feature limitation.</span></span> <span data-ttu-id="af5c1-117">För närvarande stöder lagerhanteringsprocesserna endast lager som ägs av den juridiska personen.</span><span class="sxs-lookup"><span data-stu-id="af5c1-117">Currently, warehouse management processes support only inventory that is owned by the legal entity.</span></span>
