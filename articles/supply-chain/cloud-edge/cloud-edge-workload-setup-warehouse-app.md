---
title: Konfigurera mobilappen Warehouse Management för moln- och kantskalningsenheter
description: Denna artikel förklarar hur du konfigurerar dina Warehouse Management-mobilappar för lagerställen som betjänas av en moln- eller kantskalningsenhet.
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
ms.openlocfilehash: 86edef2dfa6e9c71c04d50f185148be3a622fea1
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8865250"
---
# <a name="configure-the-warehouse-management-mobile-app-for-cloud-and-edge-scale-units"></a>Konfigurera mobilappen Warehouse Management för moln- och kantskalningsenheter

[!include [banner](../includes/banner.md)]

Denna artikel förklarar hur du konfigurerar dina Warehouse Management-mobilappar så att de kan användas på lagerställen som betjänas av en moln- eller kantskalningsenhet.

## <a name="prerequisites"></a>Förutsättningar

Innan du börjar konfigurera dina mobila enheter för anslutning till en molnbaserad eller kantskalningsenhet måste du bekräfta att de kan ansluta till företagshubben. För instruktioner, se [Installera och anslut mobilappen Warehouse Management](../warehousing/install-configure-warehouse-management-app.md).

## <a name="additional-setup-when-you-run-the-warehouse-management-mobile-app-against-a-scale-unit"></a>Ytterligare inställningar när du kör mobilappen Warehouse Management mot en skalningsenhet

Som en del av [distributionsprocess för arbetsbelastningar för skalningsenheter på lagerställe](cloud-edge-landing-page.md#scale-unit-manager-portal), det mesta av den data som krävs för att ansluta dina mobilappen Warehouse Management synkroniseras automatiskt från företagshubben till skalningsenheten. Du måste dock ange uppgifterna på sidan **Azure Active Directory appar** (**Systemadministration \> Inställningar \> Azure Active Directory appar**) på distributionen av skalningsenheten. Du kanske dessutom måste uppdatera standardvärdet **Företag** för användar-ID:t eller skapa en ny användare. Användare som är associerade med ett företag som inte finns på en distribution av en skalningsenhet kommer inte att kunna logga in när mobilappen Warehouse Management är ansluten till den skalningsenheten.

> [!NOTE]
> Eftersom data på sidan **Azure Active Directory appar** inte synkroniseras, måste du underhålla dessa data manuellt om du vill flytta din arbetsbelastning på lagret till en annan skalningsenhet.

Kom ihåg att, som en del av anslutningskonfigurationen för varje mobilappen Warehouse Management, den angivna Azure Active Directory resurs-URL måste vara för skalningsenheten istället för företagshubben.
