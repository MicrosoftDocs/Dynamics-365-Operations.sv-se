---
title: Konfigurera mobilappen Warehouse Management för moln- och kantskalningsenheter
description: Det här avsnittet förklarar hur du konfigurerar dina mobilappen Warehouse Management för lagerställen som betjänas av en moln- eller kantskalningsenhet.
author: perlynne
ms.date: 12/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysAADClientTable, SysUserManagement
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: perlynne
ms.search.validFrom: 2022-01-31
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: 1fa00b40db2f6246029876964dca9d3229567848
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/31/2022
ms.locfileid: "8071663"
---
# <a name="configure-the-warehouse-management-mobile-app-for-cloud-and-edge-scale-units"></a>Konfigurera mobilappen Warehouse Management för moln- och kantskalningsenheter

[!include [banner](../includes/banner.md)]

Det här avsnittet förklarar hur du konfigurerar dina mobilappen Warehouse Management så att de kan användas på lagerställen som betjänas av en moln- eller kantskalningsenhet.

## <a name="prerequisites"></a>Förutsättningar

Innan du börjar ställa in dina mobila enheter för anslutning till en molnbaserad eller kantskalningsenhet måste du bekräfta att de kan ansluta till företagsnavet. För instruktioner, se [Installera och anslut mobilappen Warehouse Management](../warehousing/install-configure-warehouse-management-app.md).

## <a name="additional-setup-when-you-run-the-warehouse-management-mobile-app-against-a-scale-unit"></a>Ytterligare inställningar när du kör mobilappen Warehouse Management mot en skalningsenhet

Som en del av [distributionsprocess för arbetsbelastningar för skalningsenheter på lagerställe](cloud-edge-landing-page.md#scale-unit-manager-portal), det mesta av den data som krävs för att ansluta dina mobilappen Warehouse Management synkroniseras automatiskt från företagsnavet till skalningsenheten. Du måste dock ange uppgifterna på sidan **Azure Active Directory appar** (**Systemadministration \> Inställningar \> Azure Active Directory appar**) på distributionen av skalningsenheten. Du kanske dessutom måste uppdatera standardvärdet **Företag** för användar-ID:t eller skapa en ny användare. Användare som är associerade med ett företag som inte finns på en distribution av en skalningsenhet kommer inte att kunna logga in när mobilappen Warehouse Management är ansluten till den skalningsenheten.

> [!NOTE]
> Eftersom data på sidan **Azure Active Directory appar** inte synkroniseras, måste du underhålla dessa data manuellt om du vill flytta din arbetsbelastning på lagret till en annan skalningsenhet.

Kom ihåg att, som en del av anslutningskonfigurationen för varje mobilappen Warehouse Management, den angivna Azure Active Directory resurs-URL måste vara för skalningsenheten istället för företagsnavet.
