---
title: Inloggningslänken omdirigerar tillbaka till en näthandelsplats
description: Denna artikel innehåller felsökningsvägledning som kan vara till hjälp när en inloggningslänk omdirigeras tillbaka till näthandelsplatsen istället för att gå till inloggningssidan.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 5274599ee5ea23c18648d95431b2e79ebca12dea
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8860228"
---
# <a name="sign-in-link-redirects-back-to-an-e-commerce-site"></a>Inloggningslänken omdirigerar tillbaka till en näthandelsplats

[!include [banner](../../includes/banner.md)]

Denna artikel innehåller felsökningsvägledning som kan vara till hjälp när en inloggningslänk omdirigeras tillbaka till näthandelsplatsen istället för att gå till inloggningssidan.

## <a name="description"></a>beskrivning

När du har konfigurerat en ny Microsoft Azure Active Directory B2C (Azure AD B2C) innehavare i Commerce-webbplatsbyggaren, användare som väljer länkar **Inloggning** omdirigeras tillbaka till huvudsidan för näthandel utan att gå till inloggningssidan.

## <a name="resolution"></a>Upplösning

### <a name="confirm-that-the-reply-url-is-correctly-configured-in-the-azure-ad-b2c-application"></a>Bekräfta att svars-URL är korrekt konfigurerat i Azure AD B2C-programmet

Bekräfta att svars-URL är korrekt konfigurerat i Azure AD B2C-programmet med dessa steg.

1. Gå till [Azure-portal](https://portal.azure.com/).
1. Välj det Azure AD B2C-program som du skapat för din webbplatsåtkomst.
1. Välj det program som du skapade under Azure AD B2C-inställningen.
1. Under **Svars-URL** ska du se till att listan innehåller poster för både URL-adressen och URL-adressen som genereras av näthandel, enligt exemplet i följande illustration.

    ![URL-poster för Azure AD B2C-svar.](media/aad-b2c-reply-url.jpg)

> [!NOTE]
> Både webbadressen och URL-adressen som genereras av näthandel måste vara i ett giltigt URL-format som inte innehåller inledande eller avslutande snedstreck.

## <a name="additional-resources"></a>Ytterligare resurser

[Registrera en webbapp i Azure Active Directory B2C](/azure/active-directory-b2c/tutorial-register-applications?tabs=app-reg-ga#register-a-web-application)

[Ställa in en B2C-klientorganisation i Commerce](../set-up-b2c-tenant.md)