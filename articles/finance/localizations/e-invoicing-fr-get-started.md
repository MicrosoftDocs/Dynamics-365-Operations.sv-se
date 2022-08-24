---
title: Kom i gång med tillägget för elektronisk fakturering för Frankrike
description: Den här artikeln innehåller information som hjälper dig att komma igång med tillägget elektronisk fakturering för Frankrike.
author: dkalyuzh
ms.date: 07/07/2022
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2022-00-02
ms.dyn365.ops.version: AX 10.0.29
ms.openlocfilehash: 365316b204b6d76fa6ee6b2402fefee50c8ff3ef
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/02/2022
ms.locfileid: "9220671"
---
# <a name="get-started-with-the-electronic-invoicing-add-on-for-france"></a>Kom i gång med tillägget för elektronisk fakturering för Frankrike

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Den här artikeln innehåller information som hjälper dig att komma igång med elektronisk fakturering för Frankrike. Den guidar dig genom de konfigurationssteg som är landsberoende i RCS (Regulatory Configuration Service). De här stegen kompletterar stegen som beskrivs i [Tillägget Kom igång med elektronisk fakturering](e-invoicing-get-started.md).

## <a name="country-specific-configuration-for-french-chorus-pro-submission-fr-electronic-invoicing-feature"></a>Landsspecifik konfiguration för inlämning av fransk Chorus Pro (FR) Elektronisk faktureringsfunktion

Vissa steg måste göras för att konfigurera funktionen **inlämning av fransk Chorus Pro (FR)** elektronisk fakturering. Några av parametrarna från konfigurationen publiceras med standardvärden. Dessa värden måste granskas och uppdateras så att de bättre avspeglar verksamheten.

### <a name="prerequisites"></a>Förutsättningar

Innan du kan inleda procedurerna i detta ämne måste följande förutsättningar finnas på plats:

- Bekanta dig med elektronisk fakturering. Mer information finns i [Översikt över elektronisk fakturering](e-invoicing-service-overview.md).
- Registrera dig för RCS och konfigurera e-fakturering. Mer information finns i följande artiklar:

    - [Översikt över registrering och installation av tjänsten för e-fakturering](e-invoicing-sign-up-install.md)
    - [Konfigurera Azure-resurser för e-fakturering](e-invoicing-set-up-azure-resources.md)
    - [Installera tillägget för mikrotjänster i Lifecycle Services](e-invoicing-install-add-in-microservices-lcs.md)
    - [Aktivera integreringen med elektronisk fakturering](e-invoicing-activate-setup-integration.md) – Använd informationen i den här artikeln för att aktivera integrationen mellan dina Microsoft Dynamics 365 Finance eller Dynamics 365 Supply Chain Management appen och tjänsten Elektronisk fakturering.
    - [NAF-koder och Siret-nummer](emea-fra-naf-codes-siret-numbers.md) och [Ange NAF-koder och Siret-nummer](tasks/fr-00003-naf-codes-siret-numbers.md) – Använd informationen i dessa artiklar för att ställa in NAF-koder och Siret-nummer i dina juridiska personer. 

- Din organisation måste vara registrerad för att fungera med Chorus Pro. Microsoft tillhandahåller integration med Chorus Pro i OAuth2-läge via ett API (Application Programming Interface). För detaljerad information om Chorus Pro-registrering och appaktivering, se [officiella dokumentationen](https://communaute.chorus-pro.gouv.fr/documentation/help-for-api-developers-in-oauth2-mode/).

    Följ dessa steg för att registrera med Chorus Pro.

    1. Gå till [PISTE-portal](https://piste.gouv.fr/en/component/apiportal/registration) för att starta registreringen. 
    2. Registrera ett program och aktivera OAuth-autentiseringsuppgifter (Open Authorization).
    3. Kopiera och spara klient-ID:t för OAuth-autentiseringsuppgifterna och den hemliga nyckeln. Den här informationen använder du senare.
    4. Gå till [Chorus Pro-portal](https://portail.chorus-pro.gouv.fr/aife_csm/?id=aife_enrollment) för att registrera dig. 
    5. Skapa ett teknisk konto för API-åtkomst. Mer information finns i [Skapa ett teknisk konto för API-åtkomst i produktion](https://communaute.chorus-pro.gouv.fr/documentation/creation-of-a-technical-account-for-an-api-access-in-production/).
    6. Kopiera användar-ID:t för det tekniska kontot och lösenordet. Den här informationen använder du senare.

## <a name="country-specific-configuration-of-the-application-setup-for-the-french-chorus-pro-submission-fr-electronic-invoicing-feature"></a>Landsspecifik konfiguration av appinställningen för elektronisk fakturafunktion inlämning av fransk Chorus Pro (FR)

Vissa av parametrarna från funktionen för **inlämning av fransk Chorus Pro (FR)** publiceras med standardvärden. Innan du distribuerar funktionen för e-fakturering till tjänstemiljön ska du granska standardvärdena och uppdatera dem så att de ger en bättre bild av dina affärsåtgärder.

1. Skapa hemligheter och motsvarande referens till dem i Azure-nyckelvalvet. Mer information finns i [Kundintyg och hemligheter](e-invoicing-customer-certificates-secrets.md).
2. Importera den senaste versionen av globaliseringsfunktionen **inlämning av fransk Chorus Pro (FR)** enligt beskrivet i [Importera funktioner från den globala databasen](e-invoicing-import-feature-global-repository.md).
3. Skapa en kopia av den importerade globaliseringsfunktionen och välj din konfigurationsprovider. För mer information, se [Skapa en globaliseringsfunktion](e-invoicing-create-new-globalization-feature.md).
4. I fliken **Versioner** bekräftar du att versionen **Utkast** har valts.
5. På fliken **Inställningar** i rutnätet väljer du funktionsinställningen **UBL Härledd försäljningsfaktura**.
6. Välj **Redigera** och sedan på fliken **Bearbetar pipeline** i avsnittet **Bearbetar pipeline** välj **(förhandsversion) Integrera med franska Chorus Pro** med åtgärdsnamnet **inlämning av fransk Chorus Pro**.
7. I avsnittet **Parametrar**, i fältet **Klient-ID och hemligt namn**, väljer du det filnamn du skapade för klient-ID:t i nyckelvalvet.
8. I avsnittet **Hemligt namn för klienthemlighet** välj hemlighetsnamnet du skapade för klienthemligheten i nyckelvalvet.
9. I avsnittet **Hemligt namn för teknisk inloggning** välj hemlighetsnamnet du skapade för teknisk inloggning på kontot i nyckelvalvet.
10. I avsnittet **Hemligt namn för tekniskt lösenord** välj hemlighetsnamnet du skapade för tekniskt lösenord på kontot i nyckelvalvet.
11. På fliken **Bearbetar pipeline** i avsnittet **Bearbetar pipeline**, välj **Integrera med franska Chorus Pro** med åtgärdsnamnet **Status på förfrågan om franska Chorus Pro**.
12. I avsnittet **Parametrar**, i fältet **Klient-ID och hemligt namn**, väljer du det filnamn du skapade för klient-ID:t i nyckelvalvet.
13. I avsnittet **Hemligt namn för klienthemlighet** välj hemlighetsnamnet du skapade för klienthemligheten i nyckelvalvet.
14. I avsnittet **Hemligt namn för teknisk inloggning** välj hemlighetsnamnet du skapade för teknisk inloggning på kontot i nyckelvalvet.
15. I avsnittet **Hemligt namn för tekniskt lösenord** välj hemlighetsnamnet du skapade för tekniskt lösenord på kontot i nyckelvalvet.
16. Markera **Spara** och stäng sedan sidan.
17. Upprepa steg 6 till och med 16 för funktionsinställningen **UBL Härledd projektfaktura**, **UBL Härledd försäljningskreditfaktura** och **UBL Härledd kreditfaktura för projekt**.

## <a name="additional-resources"></a>Ytterligare resurser

- [Tillägg för elektronisk fakturering – översikt](e-invoicing-service-overview.md)
- [Kom i gång med tjänstadministration för tillägget för elektronisk fakturering](e-invoicing-get-started-service-administration.md)
- [Kom i gång med tillägget för elektronisk fakturering](e-invoicing-get-started.md)
