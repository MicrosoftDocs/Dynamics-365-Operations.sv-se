---
title: Utöka Talent med Power Apps och Power Automate
description: Den här artikeln beskriver några exempel på tilläggsscenarier för Microsoft Dynamics 365 Human Resources som använder Microsoft Power Apps och Microsoft Power Automate.
author: negudava
manager: tfehr
ms.date: 02/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: negudava
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e6885c67f42ead34b5e10cc1b1a80a88fd2d59b9
ms.sourcegitcommit: 18e626c49ccfdb12c1484b985e3a275e51f61320
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/04/2021
ms.locfileid: "5115376"
---
# <a name="extend-with-power-apps-and-power-automate"></a>Utöka med Power Apps och Power Automate

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Den här artikeln beskriver några exempel på tilläggsscenarier för Microsoft Dynamics 365 Human Resources som använder Microsoft Power Apps och Microsoft Power Automate. Du kan importera lösningspaketet som associeras med varje exempel i din Power Apps-miljö. Du kan sedan använda paketen antingen som vägledning eller som utgångspunkt för att implementera scenarier som gäller för din organisation.

> [!IMPORTANT]
> Om du vill använda de mallar och program som beskrivs i det här avsnittet ”i befintligt skick” bör du testa dem och se till att de täcker alla de scenarier som avser implementeringen.

## <a name="prerequisites"></a>Förutsättningar

- Om du vill importera paket måste användarna ha behörighet **Environment Maker**.
- Användare måste ha en Power Apps Plan 2-licens eller en Power Apps Plan 2 bedömningslicens för att exportera eller importera appar.

## <a name="integration-with-microsoft-365-power-automate"></a>Integrering med Microsoft 365, Power Automate

Appen **Integrering med Microsoft 365** kan användas för att hämta teaminformation för inloggade användare från Microsoft 365. Den refererar medarbetare i personal för att extrahera identifieringstyper för medarbetare. Chefer kan kontrollera utgångsdatum för medarbetar-ID-typer. De kan också skicka en e-postpåminnelse om medarbetar-ID-typen förfaller. Power Automate kan integreras med Power Apps för att skicka påminnelsen. Bekräftelse kommer att skickas tillbaka till Power Apps från Power Automate när påminnelsen skickas. Identifieringstyper inkluderar körkort, pass och andra godtagbara former av ID.

Du kan utöka den här appen för andra scenarier. Exempelvis användas den för att visa semesterinformation för team, kalenderhändelser och alla teamspecifika händelser.

För att hämta appen **Integrering med Microsoft 365, Power Automate** gå till [Integrering med Microsoft 365](https://go.microsoft.com/fwlink/?linkid=2081787) på Microsoft Download Center.

## <a name="power-automate--sql-connect-and-execute"></a>Power Automate – anslut och kör SQL

Mallen **Power Automate – anslut och kör SQL** ansluter till Microsoft SQL Server och gör att SQL-frågor kan köras.

Även om den här mallen läser och uppdaterar SQL-register kan du utöka den och använda den för andra scenarier. Den kan exempelvis användas för att fylla på ett mellanlagringsregister i Dataverse med poster från SQL Server och regelbundet synkronisera mellanlagringsregister med hjälp av en stegvis distribution från SQL Server.

Den avancerade frågan är integrerad med flödet för att aktivera datatransformation och stegvis distribution.

För att hämta mallen **Power Automate – ansluta och köra SQL** gå till [Power Automate – ansluta och köra SQL](https://go.microsoft.com/fwlink/?linkid=2081789) på Microsoft Download Center.

## <a name="additional-resources"></a>Ytterligare resurser

[Appen Microsoft Power Platform](https://docs.microsoft.com/power-platform/admin/admin-documentation)</br>

[!INCLUDE[footer-include](../includes/footer-banner.md)]