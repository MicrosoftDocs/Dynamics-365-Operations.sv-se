---
title: "Översikt över elektroniska signaturer"
description: "Den här artikeln innehåller en översikt över elektroniska signaturer samt en beskrivning av hur de kan användas i Microsoft Dynamics 365 for Finance and Operations."
author: maertenm
manager: AnnBe
ms.date: 08/24/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SIGParameters, SIGProcSetup, SIGReasonCode
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 13611
ms.assetid: 98dc6b79-1895-45d8-9dd1-2c8a351b58af
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 698b938e515ff4755c2f111279cda244577ac9f3
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="electronic-signature-overview"></a>Översikt över elektroniska signaturer

[!include[banner](../includes/banner.md)]


Den här artikeln innehåller en översikt över elektroniska signaturer samt en beskrivning av hur de kan användas i Microsoft Dynamics 365 for Finance and Operations.

<a name="what-is-an-electronic-signature"></a>Vad är en elektronisk signatur?
--------------------------------

En elektronisk signatur bekräftar identiteten hos en person som ska påbörja eller godkänna en dataprocess. I vissa branscher är en elektronisk signatur lika juridiskt bindande som en handskriven signatur. 

Elektroniska signaturer är ett juridiskt krav för flera reglerade branscher som läkemedelsbranschen, livsmedelsbranschen, samt rymd- och försvarsbranschen. De krävs även för att överensstämma med reglerna i 21 CFR del 11 som utfärdades av Food and Drug Administration (FDA) i USA. 

**Obs!** En elektronisk signatur är i sig inte detsamma som en digital signatur. En elektronisk signatur ersätter helt enkelt en handskriven signatur, medan en digital signatur innehåller ytterligare säkerhetsfunktioner. Med en digital signatur kan det vara möjligt att identifiera om en annan användare eller process har manipulerat data. En digital signatur kan även verifieras och denna verifiering kan inte tillbakavisas av ägaren av certifikatet som användes för att signera data. Som beskrivs nedan har elektroniska signaturer i Microsoft Dynamics 365 for Finance and Operations en inbyggd funktion för digital signatur.

## <a name="electronic-signatures-in-dynamics-365-for-finance-and-operations"></a>Elektroniska signaturer i Dynamics 365 for Finance and Operations
I Finance and Operations kan du använda elektroniska signaturer för kritiska affärsprocesser. Vissa processer har inbyggda funktioner för elektronisk signatur. Du kan även skapa anpassade signaturkrav för alla databastabeller och fält. 

Elektroniska signaturer har en inbyggd funktion för digital signatur. Alla användare som signerar dokument måste få ett giltigt kryptografiskt certifikat. När ett dokument signeras verifieras den privata nyckeln som är associerad med certifikatet. Finance and Operations registrerar information om elektroniska signaturer i en logg för att tillhandahålla ett redovisningsspår. För att ställa in elektroniska signaturer, se [Ställ in elektroniska signaturer (uppgiftsguide)](tasks/set-up-electronic-signatures.md).

## <a name="users-who-require-access-to-electronic-signatures"></a>Användare som behöver åtkomst till elektroniska signaturer
Tre typer av användare kräver normalt säkerhetsåtkomst till elektroniska signaturer: elektronisk signaturadministratörer, undertecknare och elektronisk signaturrevisorer.

### <a name="electronic-signature-administrator"></a>Administratör för elektronisk signatur

Administratören för elektronisk signatur konfigurerar signaturkrav, allmänna parametrar och godkännare samt tar emot aviseringar när signaturverifieringen misslyckas. Som standard har en användare som tillhör säkerhetsrollen **IT-chef**, behörighet att administrera elektroniska signaturer.

### <a name="signer"></a>Undertecknare

En undertecknare tillhandahåller elektroniska signaturer för dokument och processer som kräver signaturer. Som standard har en användare som tillhör **Systemanvändare** säkerhetsrollen, behörighet att signera dokument elektroniskt. 

**Obs!** Undertecknaren kan behöva ytterligare behörigheter innan åtkomst beviljas till de data som rör dokumentet eller processen som signeras. En användare som ändrar data och sedan måste signera ändringarna måste ha behörighet att ändra data. En användare som signerar på uppdrag av en annan användare behöver eventuellt inte ha åtkomst till data. Ett exempel på den här typen av användaren är en arbetsledare som signerar en medarbetares ändringar.

### <a name="electronic-signature-auditor"></a>Revisor för elektronisk signatur

Revisorn för elektronisk signatur granskar databasloggen och den signaturgranskningslogg som finns i databasloggen. Som standard har en användare som tillhör säkerhetsrollen **IT-chef**, behörighet att granska elektroniska signaturer. 

Om du använder en annan roll än **IT-chef**, se till att tilldelas rollen följande behörigheter:

-   Visa fel för elektroniska signaturer
-   Visa databaslogg

## <a name="signing-documents-electronically"></a>Signera dokument elektroniskt
### <a name="get-a-certificate"></a>Hämta ett certifikat

Innan du signerar dokument elektroniskt i Finance and Operations måste du begära ett certifikat. 

**Obs!** Finance and Operations använder Microsoft SQL Server-funktioner för att skapa certifikat och aktivera elektronisk signering. Ingen annan infrastruktur för certifikat eller offentliga nycklar (PKI) krävs. 

När du begär ett certifikat skapas en offentlig och en privat nyckel för dig i Finance and Operations-databasen. Den privata nyckeln är krypterad med hjälp av ett lösenord som bara du känner till. När du signerar ett dokument elektroniskt, verifieras din identitet när du anger lösenordet. 

Om du vill begära ett certifikat, gå till sidan **Alternativ** och sedan till fliken **Konton** och klicka på **Hämta certifikat**. 

Ange och bekräfta det lösenord du ska använda för signeringen. Lösenordet används för att skydda din privata nyckel och godkänna användningen av certifikatet. Detta lösenord lagras inte i databasen och är inte tillgängligt för någon annan, inte ens Finance and Operations-administratören. 

Om du har glömt lösenordet som är kopplat till ditt certifikat måste certifikatet återställas. När du återställer certifikatet påverkas inte dokument som du signerat med hjälp av det föregående certifikatet. Om du vill återställa ett certifikat, gå till sidan **Alternativ** och klicka på **Återställ certifikat**.

### <a name="sign-a-document-electronically"></a>Underteckna ett dokument elektroniskt

Sidan **Signera dokument** visas när du gör en ändring som kräver en elektronisk signatur.

1.  Gå till sidan **Signera dokument** och klicka på fliken **Dokument** om du vill granska ändringarna i dokumentet.
2.  Välj en orsakskod på fliken **Signatur**.
3.  Skriv in en kommentar om en kommentar är obligatorisk.
4.  Om ditt användar-ID inte visas i fältet **Undertecknare** ska du välja det i listan.
5.  Ange din plats, om denna information är obligatorisk.
6.  Klicka på **OK**.

### <a name="sign-for-another-users-changes"></a>Underteckna en annan användares ändringar

Ibland kanske du vill att en användare ska signera en annan användares ändringar. Exempelvis kan det vara nödvändigt för en arbetsledare att signera ändringar som en medarbetare gör i en strukturlista. Använd denna procedur när du vill ange en Finance and Operations-användare som undertecknare för en annan användare. 

**Obs!** När en användare signerar en annan användares ändringar måste signaturen tillhandahållas på arbetsstationen för den användare som införde ändringen. Användaren kan inte spara ändringen förrän signaturen har tillhandahållits. 

Följ dessa steg om du vill utse godkännare.

1.  Gå till sidan **Alternativ** och sedan till fliken **Konton** och klicka på **Utse godkännare**.
2.  Välj ID för den användare som ska signera för andra användarens ändringar i fältet **Godkänn användar-ID**.
3.  Välj ID för den användare vars ändringar måste signeras i fältet **Signera för användar-ID**.





