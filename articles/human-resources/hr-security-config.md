---
title: Säkerhetskonfigurationsbegrepp för virtuella registerbaserade integrationer
description: I den här artikeln förklaras en arkitektur för att bygga en integration mellan Microsoft Dynamics 365 Human Resources och andra system.
author: twheeloc
ms.date: 11/19/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CDSIntegrationAdministration
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-10-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 219ceb0adae0cee5f74a39140ab74af9fdac1eb6
ms.sourcegitcommit: ea79bf014bbf495ac8e28db29502c8bd85a75f32
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/11/2022
ms.locfileid: "9759661"
---
# <a name="security-configuration-concepts-for-virtual-table-based-integrations"></a>Säkerhetskonfigurationsbegrepp för virtuella registerbaserade integrationer

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

I den här artikeln beskrivs en arkitektur för hur du använder [Microsoft Dataverse virtuella register (enheter)](/dev-itpro/power-platform/virtual-entities-overview) för att bygga en integration mellan ett Dynamics 365 Human Resources system som tredje part använder. Artikelns fokus ligger på säkerhetskonfigurationen, och på autentiserings- och auktoriseringsaspekterna som krävs mellan systemgränserna för att bygga ett funktionellt och säkert system.

## <a name="prerequisite-reference-articles"></a>Referensartiklar för förutsättningar

Följande artiklar ger mer information om begreppen i den här artikeln:

- [Översikt över virtuella entiteter](/dev-itpro/power-platform/virtual-entities-overview)
- [Kom igång med virtuella tabeller (enheter)](/developer/data-platform/virtual-entities/get-started-ve)
- [Använd autentisering mellan servrar för flera användare (Microsoft Dataverse)](/developer/data-platform/use-multi-tenant-server-server-authentication)
- [Använd OAuth-autentisering med Microsoft Dataverse (Dataverse)](/developer/data-platform/authenticate-oauth)
- [OAuth 2.0-klientreferenser flödar i Microsofts identitetsplattform](/azure/active-directory/develop/v2-oauth2-client-creds-grant-flow)
- [Autentisering och auktorisering](/dev-itpro/power-platform/authentication-and-authorization)

## <a name="architecture"></a>Arkitektur 

I följande arkitekturdiagram visas de större koncepten som ingår i en integration där virtuella tabeller (enheter) används.

![Virtuell registerbaserad integration.](./media/Hosts.jpg)

Nedan visas en förklaring av några av elementen i föregående diagram:

- **Microsoft** – Microsoft är värd för och driver olika Dynamics 365-produkter på uppdrag av kunder.

    - **Azure Active Directory (Azure AD) innehavare C** – En Azure AD-innehavare som ägs av Microsoft. Det är innehavare som Dynamics 365-appar är registrerade i.

- **Integrera partner**

    - **Integreringssystem** – Systemet som integreras med Dynamics 365. Det kan vara ett lönesystem eller något system som använder data som lagras i Dynamics 365.
    - **Adapter** – Den programvara eller tjänst som ansvarar för att samverka med både Dynamics 365 och integreringssystemet.

        > [!NOTE]
        > Om en adapter ska användas av flera Dynamics 365-kunder är den potentiella kunden att den registreras som ett flerdimensionellt program i Azure AD.

    - **Azure AD innehavare A** – En Azure AD innehavare som ägs av den integrerande partnern. Det är innehavare som adapterns app-ID är registrerad i.

- **Gemensam kund** – En kund som implementerar Dynamics 365 Human Resources och integrerar partnerns lösning.

    - **Dynamics 365 Finance eller personal** – Den kundspecifika instansen av Dynamics 365 Finance eller personal som innehåller kunddata som det integrerande systemet kräver.
    - **Dataverse**– Den kundspecifika Dataverse-miljön som är ansluten till Ekonomi eller Personal. Dataverse innehåller ett webb-API för interaktion med Dynamics 365-data.
    - **Azure AD innehavare B** – Kundens Azure AD innehavare. Det fungerar som ID-leverantör (auktoriseringsserver) och ut utfärdar tokens som auktoriserar anropare att ringa kundens Dataverse-instans.

## <a name="basic-request-flow"></a>Grundläggande förfrågansflöde

Det här avsnittet beskriver det grundläggande flödet för en typisk begäran som ingår i en integration. Den hänvisar till det arkitekturdiagram som beskrivs tidigare i artikeln.

En normal begäran kräver att adapterfrågan Dynamics 365 för data och sedan sparar och synkroniserar dessa data till integreringssystemet.

1. Adaptern anropar Dataverse webb-API för att fråga efter relevanta data.

    > [!NOTE]
    > Autentisering är en förutsättning, och tokenanskaffning är den stora delen av processen. Autentiseringen beskrivs i [autentisering och auktorisering vid systemgränser](#authentication-and-authorization-at-system-boundaries).

    Det här anropet görs mot Dataverse webb-API:n om du vill söka efter programdata som visas via ett virtuellt register. (Se "2. Initial synkronisering" och "3. Delta Synkronisera" i diagrammet.)

2. Dataverse hanterar begäran genom att fråga det virtuella registret via insticksprogrammet Virtuell enhet ("Virtuell tabell proxy" i diagrammet). Dataverse-begäran vidarebefordras till ekonomitjänsten eller den virtuella enhetstjänsten för att söka efter de data som har sparats fysiskt i ekonomi- eller personaldatabasen.
3. Den virtuella enhetstjänsten (Ekonomi eller Personal) översätter begäran mot den virtuella enheten till en fråga mot den ekonomi- eller personalenhet som den virtuella enheten Dataverse får tillbaka. Data hämtas från databasen, översätts tillbaka till Dataverse enhetens representation och returneras till den som ringer.
4. Adaptern slutför all nödvändig mappning och dataöversättning och anropar integreringssystemet för att bevara data i integrerande systemdatabasen. (Se "4. Spara data" i diagrammet.)

## <a name="authentication-and-authorization-at-system-boundaries"></a>Autentisering och auktorisering vid systemgränser

*Autentiseringen* verifierar att en användares eller ett programs identitet har bevisats och bekräftar att användaren eller programmet är vem han eller hon säger att de är. *Auktorisering* ger användaren eller ansökan rätt att få åtkomst till särskilda behörigheter på programnivå. Mer information finns i [Autentisering kontra auktorisering](/azure/active-directory/develop/authentication-vs-authorization).

De flesta korssystemsamtalen i det arkitekturdiagram som beskrivs tidigare i den här artikeln gäller adaptern. Adaptern måste autentiseras för att kunna göra följande anrop:

- Anrop till Dataverse
- Samtalet till integrationssystemet

Titta på systemgränser i diagrammet. Alla webbförfrågningar mellan system måste autentiseras, och auktoriseringskontroller på programnivå måste skickas innan data returneras till den som ringer. För en begäran mot ett virtuellt Dynamics 365-register som stöds av Ekonomi och Personal, tillämpas verifierings- och auktoriseringskontroller vid följande systemgränser:

- Anropet mellan adaptern och Dataverse webb-API:t (OData) slutpunkt
- Samtalet mellan insticksprogrammet Dataverse virtuell enhet och den virtuella enhetstjänsten Ekonomi eller Personal

I båda fall utförs autentiseringskontroller först. Därefter utförs auktoriseringskontroller på programnivå för att säkerställa att den autentiserade användaren eller programmet har rätt behörigheter på programnivå för att hämta begärda data.

Autentisering för samtal Dataverse hanteras via en ägartoken som måste inkluderas som en HTTP-rubrik i webbegäran till Dataverse. Adaptern måste få en token från klientorganisation B Azure AD-instansen. (Se "1. Hämta Token" i diagrammet.) Azure AD fungerar som ID-leverantör i autentiseringsflödet.

Adaptern autentiserar genom att tillhandahålla sin applikationsidentitet (icke-hemlig, som registrerad i Azure AD klientorganisation A) och en apphemlighet eller certifikat som bara adapterappen har.

När användaren eller programmet har autentiserats för att ringa samtal till Dataverse, auktoriseringskontroller Dataverse-nivå för varje begäran. Dessa kontrollerar att den som ringer (adapterprogrammets identitet, som betecknas "\<guid A\>" i diagrammet) har rätt programbehörighet. Auktoriseringen på programnivå hanteras i Dataverse via ett program som representerar adapterns program-ID. Behörigheter på programnivå hanteras genom att bevilja åtkomst till specifika Dataverse-definierade programroller. Rollerna ger finfördelningsbehörigheter för programmet.

För mer detaljerad vägledning, se [Använd autentisering mellan servrar för flera användare](/power-apps/developer/data-platform/use-multi-tenant-server-server-authentication)

Om Dataverse-tillståndskontroller på appnivån godkänns, insticksprogrammet virtuell enhet ringer till virtuell enhet-tjänstens slutpunkt i Ekonomi- eller Personal-miljön. Server till server-autentisering (S2S) används för att ringa det här samtalet. Den använder den identitet och det konfigurerade datakällposten för Ekonomi och drift.

![Konfigurationspost för Ekonomi och drift i den virtuella datakällan i den här miljön.](./media/sandbox.jpg)

Mer information finns i [Konfigurera Dataverse virtuella entiteter](/dev-itpro/power-platform/admin-reference).

Samtalet från Dataverse virtuell enhet till plugin-program till Ekonomi och Personal omfattar adapteridentiteten för det ursprungliga Dataverse från adaptern (den identitet som har angetts som "\<guid A\>" i det arkitekturdiagrammet). Om den virtuella enhetens datakälla är korrekt konfigurerad och S2S-autentiseringskontrollerna har godkänts, kommer tjänsten virtuell enhet i Ekonomi eller Personal att köra frågan i samband med den ursprungliga anroparen (adaptern, \<guid A\>). Kontroller av programbehörighet (auktorisering) på ekonomi- eller personalnivå utförs för att säkerställa att adaptern har de behörigheter som krävs för åtkomst till de dataenheter som begärs via frågan.

Ekonomi- och Personalsäkerhet hanteras på följande sätt:

1. Genom att mappa adapter-ID (\<guid A\>) till en specifik ekonomi- eller personalanvändare. Denna mappning görs på sidan **Azure Active Directory-program**. Mer information finns i [Registrera ditt externa program](/dev-itpro/data-entities/services-home-page.md#register-your-external-application).
2. Genom att bevilja ekonomi- eller personalanvändare relevanta roller, arbetsuppgifter och behörigheter på programnivå. Mer information finns i [Rollbaserad säkerhet](/dev-itpro/sysadmin/role-based-security).

Om adapterprogrammet (\<guid A\>) beviljas de behörigheter som krävs för åtkomst till begärda data, inträffar följande händelser:

1. Frågan körs.
2. Data översätts till enhetssidan Dataverse.
3. Data returneras till adaptern.

> [!IMPORTANT]
> Under utveckling kan adaptern köras med en ekonomi- eller personalanvändare med administratörsrollen. I en produktionsmiljö ska dock adaptern aldrig köras med administratörsbehörighet.

## <a name="key-takeaways"></a>Viktiga budskap

Här är några viktiga implikationer av den virtuella tabellen eller enhetsarkitekturen:

- Säkerhetskonfigurationen för virtuella register som används av Personal hanteras i Personal.
- Kunden ("Gemensam kund" i arkitekturdiagrammet tidigare i den här artikeln) har full kontroll över vilka privilegier som ges till den integrerande adapteridentiteten (betecknad "\<guid A\>" i diagrammet).
- Kunden ansvarar för korrekt säkerhetskonfiguration för sin Personalmiljö. Den integrerande partner som skapar adaptern måste ange riktlinjer för vilka behörigheter adaptern behöver.
