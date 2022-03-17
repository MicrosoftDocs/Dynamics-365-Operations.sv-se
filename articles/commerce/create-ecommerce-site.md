---
title: Skapa en näthandelssajt
description: I det här avsnittet beskrivs de steg och den information som krävs för att skapa en ny näthandelssajt i webbplatsverktyget för Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 03/04/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 5e451b1c95c3e26d1292e7b8300b62af43c81f2f
ms.sourcegitcommit: b80692c3521dad346c9cbec8ceeb9612e4e07d64
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/05/2022
ms.locfileid: "8388221"
---
# <a name="create-an-e-commerce-site"></a>Skapa en näthandelssajt

[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs de steg och den information som krävs för att skapa en ny näthandelssajt i webbplatsverktyget för Dynamics 365 Commerce.

När du licensierar Dynamics 365 Commerce-funktionerna etableras webbplatsverktyget med en startwebbplats som du kan använda som grund för din egen webbplats. Om du däremot vill börja från början eller om du vill skapa en andra plats måste du skapa en ny webbplats i redigeringsmiljön för webbplatsen. 

## <a name="site-creation-prerequisites"></a>Förutsättningar för webbplatsgenerering

En site builder-användare måste ha ett Microsoft Azure Active Directory(Azure AD)-användarkonto inkluderat i Azure AD-säkerhetsgruppen som tilldelats för administratörerna av näthandelssystemet. Mer information finns i [Distribuera en ny näthandelsklient](deploy-ecommerce-site.md).

> [!NOTE]
> Azure AD-gästanvändare kan ha olika åtkomstbehörigheter i din Azure AD-klientorganisation. Även om denne ingår i den Azure AD-säkerhetsgrupp som har tilldelats för administratörerna av näthandelssystemet kanske en gästanvändare behöver att inställningarna för Azure AD-behörigheten **Extern användare** ändras för att han/hon ska kunna skapa en näthandelsplats i Commerce. 

För att justera inställningarna för **externa användare** i Azure AD följer du dessa steg.

1. Gå till din Azure AD-klientorganisation i Azure-portalen.
1. Gå till **Användarinställningar \> Externa användare** och markera länken **Hantera externa samarbetsinställningar**. På så sätt öppnas sidan **Externa samarbetsinställningar** där inställningar för gästanvändaråtkomst, inställningar för gästinbjudan och samarbetsrestriktioner kan anges. 
1. Justera inställningarna för externt samarbete i enlighet med företagets säkerhetspolicy. 

## <a name="set-up-your-site"></a>Ställ in din webbplats

Gör följande om du vill ställa in din webbplats.

1. Öppna miljön för webbplatsverktyget. Du hittar en länk till webbplatsverktyget i Microsoft Lifecycle Services (LCS) på sidan miljöfunktioner för Commerce.
1. På startsidan för webbplatsredigeringsmiljön, välj **Ny webbplats**.
1. Ange följande information i dialogrutan **Ny webbplats**.

| Fält                               | Beskrivning |
|-------------------------------------|-------------|
| Webbplatsens namn                           | Ange visningsnamnet som ska användas för webbplatsen i webbplatsredigeringsmiljön. Det här namnet visas bara i redigeringsmiljön och kommer inte att visas för kunderna. |
| Webbplatsadministratörens säkerhetsgrupp | Ange den säkerhetsgrupp för Microsoft Azure Active Directory (Azure AD) som hanterar användare med rollen webbplatsadministratör på den här webbplatsen. |
| Standardkanal (driftenhetsnummer) | Välj den onlinebutik som den här webbplatsen ska fungera som webbskyltfönster för. Om du vill att din näthandelssajt ska stödja flera olika onlinebutiker måste du associera butikerna med din webbplats under **Webbplatsinställningar** efter det att webbplatsen har konfigurerats. |
| Standardspråk                            | Ange standardspråket för den här onlinebutiken och marknaden. En onlinebutik har stöd för flera språk. Om du vill stödja flera språk för den här onlinebutiken eller en annan onlinebutik kan du konfigurera stödet i **platsinställningar** efter att webbplatsen har konfigurerats.  |
| Domän                              | Välj ett domännamn som ska fungera som domän för denna onlinebutik. Om du inte har konfigurerat några domäner i LCS kan du lämna det här fältet tomt. När din domän har konfigurerats i LCS måste du lägga till den i din onlinebutik i **webbplatsinställningarna**.  |
| Sökväg                              | När din webbplats har stöd för mer än ett språk för ett givet domännamn, använder du sökvägsfältet för att skapa en unik webbplats-URL för den domänen och språkkombinationen. Om det språk som du har angett i fältet **Standardspråk** är det enda språk som du kommer att stödja för den här domänen, eller om det är standardspråket när du har lokaliserat platsen till ytterligare språk, rekommenderar vi att du lämnar det här fältet tomt. |

När du har skapat webbplatsen kan du kontrollera att den är kopplad till onlinebutiken genom att välja fliken **produkter**. Du bör se sortimentet av produkter som har tilldelats onlinebutiken. Du kan också använda det nedrullningsbara menyn längst upp till vänster på sidan för att komma åt de tilldelade produkterna efter kategori.

## <a name="rename-your-site"></a>Ge din webbplats ett nytt namn

Följ dessa steg för att byta namn på din webbplats i webbplatsverktyget.

1. Om du vill öppna listvyn väljer du **Webbplatsväxlare** i det övre högra hörnet och väljer **Hantera webbplatser** . 
1. Markera kryssrutan bredvid den site du vill byta namn på och välj sedan **Byt namn** i kommandofältet.
1. I dialogrutan **Nytt namn på webbplats** ange det nya namnet på webbplats och välj **OK**. Webbplatslistan uppdateras så att webbplatsens nya namn visas.

## <a name="additional-resources"></a>Ytterligare resurser

[Konfigurera ditt domännamn](configure-your-domain-name.md)

[Distribuera en ny klientorganisation för näthandel](deploy-ecommerce-site.md)

[Associera en Dynamics 365 Commerce-webbplats med en onlinekanal](associate-site-online-store.md)

[Hantera robots.txt-filer](manage-robots-txt-files.md)

[Överför URL-omdirigeringar i bulk](upload-bulk-redirects.md)

[Ställa in en B2C-innehavare i Commerce](set-up-B2C-tenant.md)

[Ställa in anpassade sidor för användarinloggningar](custom-pages-user-logins.md)

[Konfigurera flera B2C-innehavare i en Commerce-miljö](configure-multi-B2C-tenants.md)

[Lägga till stöd för ett innehållsleveransnätverk (CDN)](add-cdn-support.md)

[Aktivera platsbaserad butiksdetektering](enable-store-detection.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
