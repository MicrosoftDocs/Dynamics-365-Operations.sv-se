---
title: Det går inte att flytta ID-nummer om Tom utleverans och Tom inleverans tillåts
description: Det går inte att flytta ett ID-nummer om serienumret har Tom utleverans och Tom inleverans tillåten. Du korrigerar detta genom att göra serienummerfältet valfritt.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 0047f79aa417c8fc910447505f07963d014f54e7
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477624"
---
# <a name="cant-move-license-plate-if-serial-number-has-blank-issue-and-blank-receipt-allowed"></a>Det går inte att flytta ett ID-nummer om serienumret har Tom utleverans och Tom inleverans tillåten

## <a name="symptoms"></a>Symtom

Du kan inte flytta ett ID-nummer genom att använda menyartikeln **Rörelse** om ett serienummer har inställningen *Tom utleverans tillåten* och *Tom inleverans tillåten* på spårningsdimensionsgruppen och om det finns flera ID-nummer på samma plats, varav några har serienummer och andra inte har dem.

## <a name="resolution"></a>Lösning

Det här problemet kommer att åtgärdas genom ändringar som distribueras i [KB-4571546](https://fix.lcs.dynamics.com/Issue/Details?kb=4571546&bugId=467880&dbType=3&qc=5b46d7faa9cc326cebfe9854cb30be8ea30b21ef33d3572c325fbb21202de687). Dessa ändringar gör fältet **Serienummer** valfritt när en tom inleverans och en tom utleverans är tillåten.
