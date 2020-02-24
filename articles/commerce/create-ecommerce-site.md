---
title: Skapa en e-handelsplats
description: I det här avsnittet beskrivs de steg och den information som krävs för att skapa en ny e-handelswebbplats i Dynamics 365 Commerce webbplatsskaparen.
author: bicyclingfool
manager: AnnBe
ms.date: 01/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 3d3d8a290f06d9734be21f2d59152acac6857506
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/01/2020
ms.locfileid: "3002023"
---
# <a name="create-an-e-commerce-site"></a>Skapa en e-handelsplats


[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs de steg och den information som krävs för att skapa en ny e-handelswebbplats i Dynamics 365 Commerce webbplatsskaparen.

Innan du börjar utveckla din näthandelsplats måste du först skapa en ny webbplats i webbplatsskaparen. 


Innan du börjar utveckla din näthandelsplats måste du först skapa en ny webbplats i webbplatsredigeringsmiljön. Innan du kan skapa en ny plats måste minst en onlinebutik skapas i Handel. 


## <a name="set-up-your-site"></a>Ställ in din webbplats

Gör följande om du vill ställa in din webbplats.

1. Öppna miljön för webbplatsskaparen. Du hittar en länk till webbplatsskaparen i Microsoft Lifecycle Services (LCS) på sidan miljöfunktioner för Handel.
1. På startsidan för webbplatsredigeringsmiljön, välj **Ny webbplats**.
1. Ange följande information i dialogrutan **Ny webbplats**.

| Fält                               | Beskrivning |
|-------------------------------------|-------------|
| Webbplatsens namn                           | Ange visningsnamnet som ska användas för webbplatsen i webbplatsredigeringsmiljön. Det här namnet visas bara i redigeringsmiljön och kommer inte att visas för kunderna. |
| Webbplatsadministratörens säkerhetsgrupp | Ange den säkerhetsgrupp för Microsoft Azure Active Directory (Azure AD) som hanterar användare med rollen webbplatsadministratör på den här webbplatsen. |
| Standardkanal (driftenhetsnummer) | Välj den onlinebutik som den här webbplatsen ska fungera som webbskyltfönster för. Om du vill att din näthandelsplats ska stödja flera onlinebutiker måste du associera butikerna med din webbplats i **webbplatsinställningar** när webbplatsen har konfigurerats. |
| Standardspråk                            | Ange standardspråket för den här onlinebutiken och marknaden. En onlinebutik har stöd för flera språk. Om du vill stödja flera språk för den här onlinebutiken eller en annan onlinebutik kan du konfigurera stödet i **platsinställningar** efter att webbplatsen har konfigurerats.  |
| Domän                              | Välj ett domännamn som ska fungera som domän för denna onlinebutik. Om du inte har konfigurerat några domäner i LCS kan du lämna det här fältet tomt. När din domän har konfigurerats i LCS måste du lägga till den i din onlinebutik i **webbplatsinställningarna**.  |
| Sökväg                              | När din webbplats har stöd för mer än ett språk för ett givet domännamn, använder du sökvägsfältet för att skapa en unik webbplats-URL för den domänen och språkkombinationen. Om det språk som du har angett i fältet **Standardspråk** är det enda språk som du kommer att stödja för den här domänen, eller om det är standardspråket när du har lokaliserat platsen till ytterligare språk, rekommenderar vi att du lämnar det här fältet tomt. |


När du har skapat webbplatsen kan du kontrollera att den är kopplad till onlinebutiken genom att välja fliken **produkter**. Du bör se sortimentet av produkter som har tilldelats onlinebutiken. Du kan också använda det nedrullningsbara menyn längst upp till vänster på sidan för att komma åt de tilldelade produkterna efter kategori.

## <a name="additional-resources"></a>Ytterligare resurser

[Konfigurera ditt domännamn](configure-your-domain-name.md)

[Distribuera en ny näthandelsplats](deploy-ecommerce-site.md)

[Associera en online-webbplats med en kanal](associate-site-online-store.md)

[Hantera robots.txt-filer](manage-robots-txt-files.md)

[Ställa in anpassade sidor för användarinloggningar](custom-pages-user-logins.md)

[Lägga till stöd för ett innehållsleveransnätverk (CDN)](add-cdn-support.md)

[Aktivera platsbaserad butiksdetektering](enable-store-detection.md)
