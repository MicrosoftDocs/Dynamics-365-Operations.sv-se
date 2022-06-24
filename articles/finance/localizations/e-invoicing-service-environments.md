---
title: Tjänstmiljöer
description: Detta ämne tillhandahåller information om tjänstemiljöer för e-fakturering samt förklarar hur du konfigurerar dessa.
author: dkalyuzh
ms.date: 02/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkalyuzh
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 8c743c5b2fbc7dcc3ae04fa4d7ca0e65de6c2507
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8901259"
---
# <a name="service-environments"></a>Tjänstmiljöer

[!include [banner](../includes/banner.md)]

Tjänstemiljöer är logiska partitioner som skapas för att stödja globaliseringsfunktionerna samt tillhörande dokument som bearbetas i tjänsten e-fakturering. Säkerhetshemligheter, digitala certifikat och åtkomstbehörigheter (styrning) måste konfigureras på tjänstemiljönivå.

Du kan skapa så många tjänstemiljöer som du behöver. Alla tjänstemiljöer som du skapar är oberoende av varandra. Vi rekommenderar att du skapar minst två tjänstemiljöer:

- En miljö för huvudutvecklings- och valideringssyften. Den här miljön är vanligtvis en UAT-miljö (User Acceptance Testing).
- En miljö för produktion. Den här miljön är vanligtvis en produktionsmiljö.

Den här typen av partitionering underlättar validering och anpassning av e-faktureringsprocesserna innan de går till produktion.

Servicemiljöer måste skapas och underhållas i Regulatory Configuration Service (RCS). När dessa sedan är klara måste de publiceras i tjänsten e-fakturering. Under publiceringsprocessen skickas parametrarna för servicemiljön från RCS-instansen till e-faktureringstjänsten.

Om du inte slutför publiceringsprocessen efter att du har skapat en ny servicemiljö eller justerat en befintlig servicemiljö (till exempel genom att lägga till eller ta bort användare eller hemligheter för Microsoft Azure Key Vault), gäller inte ändringarna. Endast publicerade miljöer kan nås av eller Dynamics 365 Finance eller Dynamics 365 Supply Chain Management.

## <a name="service-environment-statuses"></a>Statustyper för tjänstemiljö

Tjänstemiljöer kan hanteras via sin status. Du kan visa statusen för en miljö på sidan **Servicemiljöer**. Följande statusalternativ finns tillgängliga:

- **Ej publicerad** – Miljön har skapats men ännu inte publicerats.
- **Publicerad** – Miljön har publicerats i tjänsten e-fakturering.
- **Ändrat** – Attributen för en publicerad miljö har ändrats, men ändringarna har ännu inte publicerats.

## <a name="users"></a>Användare

Varje tjänstemiljö måste visa en lista över de användare som kan ansluta till e-fakturering från Ekonomi eller Supply Chain Management.

## <a name="applications"></a>Ansökningar

I vissa situationer kanske andra program än Ekonomi eller Supply Chain Management måste ansluta till tjänsten e-fakturering för att skicka elektroniska dokument för vidare bearbetning eller för att hämta information som t.ex. sändningsstatus för ett dokument. I dessa scenarier ska programmet definieras i listan över program. På detta sätt har det åtkomst till e-faktureringstjänsten. Programmet måste även registreras som ett program i Azure Active Directory (Azure AD), och objekt-ID måste användas för att identifiera det. 

Eftersom Microsoft kräver en säkerhetskontroll på hög nivå över program som kan ansluta till e-faktureringstjänsten måste du kontakta Microsoft på <DGXRegulatoryservicesengineering@service.microsoft.com> och ange följande information om programmet:

- Klientorganisations-ID för Azure AD
- Miljö-ID för Microsoft Dynamics Lifecycle Services (LCS)
- Program-ID (klient-ID)
- Objekt-ID
- Justering och en beskrivning på hög nivå av programmet

Microsoft utvärderar begäran och registrerar programmet i säkerhetsregistret för att säkerställa att det kan användas med e-fakturering.

## <a name="number-sequences"></a>Nummerserier

Om dina scenarier kräver nummerserier (till exempel i filnamn) kan du använda nummerserier som är definierade för en specifik miljö, men som kan användas antingen över globaliseringsfunktionerna eller för en specifik globaliseringsfunktion. När en nummerserie har definierats kan du använda den i variabler och bearbeta förlopp. Du spårar användningen genom att, på sidan **Nummerserier**, söka efter värdet **Aktuella** för parametern **Används**.

### <a name="working-with-number-sequences"></a>Arbeta med nummerserier
På sidan **Nummerserier**: 

- Skapa en ny nummerserie genom att välja **Nytt**. Ange sedan ett namn och en beskrivning. 
- Välj **Ta bort** om du vill ta bort en nummerserie som inte längre används.
- Du behöver inte välja **Publicera** i åtgärdsfönstret för att publicera ändringarna i en nummerserie. Uppdateringen sker automatiskt.

## <a name="create-a-key-vault-reference"></a>Skapa en nyckelvalvsreferens

1. Logga in på RCS-kontot.
2. I arbetsytan **globaliseringsfunktion** i avsnittet **Miljöer**, välj panelen **e-fakturor**.
3. På sidan **Miljökonfiguration** väljer du **Tjänstemiljöer** i åtgärdsfönstret.
4. På sidan **Tjänstemiljöer** väljer du **Parametrar för nyckelvalv** i åtgärdsfönstret.
5. På sidan **Parametrar för nyckelvalv** väljer du **Ny** för att skapa en nyckelvalvsreferens.
6. I fältet **Namn** anger du namnet på nyckelvalvsreferensen.
7. Ange en beskrivning i fältet **beskrivning**.
8. I fältet **URI för nyckelvalv** klistrar du in URI för Key Vault från nyckelvalvet (`https://<your key vault>.vault.azure.net/`). Mer information finns i [Skapa ett Azure-nyckelvalv i Azure-portalen](e-invoicing-create-azure-key-vault-azure-portal.md).
9. Välj **Spara**.
    
## <a name="create-a-secret-for-the-storage-account-secret-token"></a>Skapa en hemlighet för lagringskontots hemlighetstoken

1. På sidan **Parametrar för nyckelvalv** väljer du den nyckelvalvsreferens som du skapade i föregående procedur innan du i avsnittet **Certifikat** väljer **Lägg till**.
2. I fältet **Namn** anger du namnet för lagringskontots hemlighet. Detta namn ska matcha namnet på den Key Vault-hemlighet som innehåller lagringstoken för signatur för delad åtkomst (SAS). Mer information finns i [Skapa ett Azure-lagringskonto i Azure-portalen](e-invoicing-create-azure-storage-account-azure-portal.md). 
3. Ange en beskrivning i fältet **beskrivning**.
4. Välj **Typ** i fältet **Hemlighet**.
5. Välj **Spara**.
    
## <a name="create-a-service-environment"></a>Skapa en tjänstemiljö

1. På sidan **Tjänstemiljöer** väljer du **Ny** om du vill skapa en tjänstemiljö.
2. I fältet **Namn** anger du namnet på miljön för e-fakturering.
3. Ange en beskrivning i fältet **beskrivning**.
4. I fältet **Lagringshemlighet för SAS-token** väljer du namnet på lagringskontots hemlighet som måste användas för att ge åtkomst till lagringskontot.
5. I avsnittet **Användare** väljer du **Lägg till** om du vill lägga till en användare som är behörig att skicka in e-fakturor via miljön samt även ansluta till lagringskontot.
6. I fältet **Användar-ID** anger du användarens alias. 
7. I fältet **E-postadress** anger du användarens e-postadress.
8. Välj **Spara**.
9. I åtgärdsfönstret väljer du **Publicera** för att publicera miljön i tjänsten för e-fakturering. Bekräfta att värdet i fältet **Status** ändras till **Publicerad**.
