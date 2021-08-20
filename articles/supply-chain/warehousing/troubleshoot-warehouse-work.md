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
ms.openlocfilehash: f9dbc1e043de5c8f840b291b652ec522c9f1eb6a622e8dab88ced3fa91570e8e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6775469"
---
# <a name="troubleshoot-warehouse-work"></a>Felsöka distributionslagerarbete

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur du åtgärdar vanliga problem som kan uppstå när du arbetar med lagerarbete i Microsoft Dynamics 365 Supply Chain Management.

## <a name="i-cant-move-license-plates-that-have-serial-number-items-when-blank-issue-and-blank-receipt-are-allowed-on-the-tracking-dimension-group"></a>Jag kan inte flytta ID-nummer som har serienummerartiklar när en tom utleverans och en tom inleverans är tillåten på spårningsdimensionsgruppen.

### <a name="issue-description"></a>Problembeskrivning

Du kan inte flytta ett ID-nummer genom att använda menyartikeln **Rörelse** om ett serienummer har inställningen *Tom utleverans tillåten* och *Tom inleverans tillåten* på spårningsdimensionsgruppen och om det finns flera ID-nummer på samma plats, varav några har serienummer och andra inte har dem.

### <a name="issue-resolution"></a>Problemlösning

Det här problemet kommer att åtgärdas genom ändringar som distribueras i [KB-4571546](https://fix.lcs.dynamics.com/Issue/Details?kb=4571546&bugId=467880&dbType=3&qc=5b46d7faa9cc326cebfe9854cb30be8ea30b21ef33d3572c325fbb21202de687). Dessa ändringar gör fältet **serienummer** valfritt när en tom inleverans och en tom utleverans är tillåten.

## <a name="i-receive-the-following-error-message-in-the-warehouse-management-mobile-app-when-i-process-movements-the-inventory-owner-1-is-not-allowed-in-this-process"></a>Jag får följande felmeddelande i modulen mobilappen för distributionslagerhantering när jag bearbetar transporter: "lagrets ägare %1 är inte tillåten i den här processen".

### <a name="issue-description"></a>Problembeskrivning

Spårningsdimensionen **Ägare** spårningsdimension saknas när mobilappen för distributionslagerhantering används för att göra rörelser. En vanlig lageröverföringsjournal från klienten Supply Chain Management visas som avsett arbete och kan endast bokföras om dimensionen **Ägare** fylls i.

### <a name="issue-resolution"></a>Problemlösning

Microsoft har utvärderat det här problemet och har fastställt att det är en funktionsbegränsning. För närvarande stöder lagerhanteringsprocesserna endast lager som ägs av den juridiska personen.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]