---
title: Inloggningslänken omdirigerar tillbaka till en e-handelsplats
description: Det här avsnittet innehåller felsökningsvägledning som kan vara till hjälp när en inloggningslänk omdirigeras tillbaka till e-handelsplatsen istället för att gå till inloggningssidan.
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
ms.openlocfilehash: a1d0ae4e487c391020947c607d5d7cb5d1ba6af4
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020613"
---
# <a name="sign-in-link-redirects-back-to-an-e-commerce-site"></a>Inloggningslänken omdirigerar tillbaka till en e-handelsplats

[!include [banner](../../includes/banner.md)]

Det här avsnittet innehåller felsökningsvägledning som kan vara till hjälp när en inloggningslänk omdirigeras tillbaka till e-handelsplatsen istället för att gå till inloggningssidan.

## <a name="description"></a>beskrivning

När du har konfigurerat en ny Microsoft Azure Active Directory B2C (Azure AD B2C) innehavare i Commerce-webbplatsbyggaren, användare som väljer länkar **Inloggning** omdirigeras tillbaka till huvudsidan för e-handel utan att gå till inloggningssidan.

## <a name="resolution"></a>Upplösning

### <a name="confirm-that-the-reply-url-is-correctly-configured-in-the-azure-ad-b2c-application"></a>Bekräfta att svars-URL är korrekt konfigurerat i Azure AD B2C-programmet

Bekräfta att svars-URL är korrekt konfigurerat i Azure AD B2C-programmet med dessa steg.

1. Gå till [Azure-portal](https://portal.azure.com/).
1. Välj det Azure AD B2C-program som du skapat för din webbplatsåtkomst.
1. Välj det program som du skapade under Azure AD B2C-inställningen.
1. Under **Svars-URL** ska du se till att listan innehåller poster för både URL-adressen och URL-adressen som genereras av e-handel, enligt exemplet i följande illustration.

    ![URL-poster för Azure AD B2C-svar](media/aad-b2c-reply-url.jpg)

> [!NOTE]
> Både webbadressen och URL-adressen som genereras av e-handel måste vara i ett giltigt URL-format som inte innehåller inledande eller avslutande snedstreck.

## <a name="additional-resources"></a>Ytterligare resurser

[Registrera en webbapp i Azure Active Directory B2C](/azure/active-directory-b2c/tutorial-register-applications?tabs=app-reg-ga#register-a-web-application)

[Ställa in en B2C-klientorganisation i Commerce](../set-up-b2c-tenant.md)