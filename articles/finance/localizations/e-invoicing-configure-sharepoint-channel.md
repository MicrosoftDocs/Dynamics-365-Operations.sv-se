---
title: Konfigurera en SharePoint-kanal
description: I denna artikel beskrivs hur du konfigurerar en Microsoft SharePoint-kanal för bearbetning av inkommande e-fakturor.
author: dkalyuzh
ms.date: 02/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom:
- "97423"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 89538adde4d14212fb0deccad05f828d146f16db
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8910053"
---
# <a name="configure-a-sharepoint-channel"></a>Konfigurera en SharePoint-kanal

[!include [banner](../includes/banner.md)]

En förutsättning för att du ska kunna konfigurera en Microsoft SharePoint-kanal för att bearbeta inkommande dokument är att utföra stegen som beskrivs i [Konfigurera en SharePoint-anslutning](e-invoicing-create-sharepoint-connection.md).

Du kan sedan använda SharePoint-kanalen för att importera elektroniska leverantörsfakturor från filer som lagras i dina SharePoint-mappar.

1. Skapa följande mappar på din SharePoint-webbplats:

    - **Huvudmapp** – Mappen som tjänsten ska bearbeta filer från.
    - **Arkivmapp** – Mappen där bearbetade filer kommer att lagras.
    - **Felmapp** – Mappen som systemet flyttar filerna till om bearbetningen misslyckas.

2. I Regulatory Configuration Service (RCS) väljer du den funktion för e-fakturering som du skapade. Se till att du väljer den version som har statusen **Utkast**.
3. På fliken **Inställningar** väljer du **Lägg till**.
4. I listrutedialogen **Skapa funktionsinställning**, i fältgruppen **Ny**, väljer du alternativet **Anpassade inställningar**.
5. I fältgruppen **Installationstyp** väljer du alternativet **Datakanal**.
6. I fältet **Välj datakanal** väljer du **SharePoint-mapp**.
7. Markera **Skapa**.
8. Markera den rad som du skapade tidigare och välj sedan **Redigera**.
9. På fliken **Datakanal**, i avsnittet **Parametrar**, ställer du in följande obligatoriska fält.

    | Fält                 | Beskrivning |
    |-----------------------|-------------|
    | Datakanal          | Ange ett unikt namn för att identifiera datakanalen. Namnet kan ha maximalt 10 tecken. Det refereras till i tillämplighetsreglerna och i anslutna program under kommunikationsprocessen. |
    | SharePoint-adress    | Ange SharePoint-URL. Ange exempelvis `<domain>.sharepoint.com`. |
    | Program-ID        | Ange namnet på den Azure Key Vault-hemlighet som innehåller ID för SharePoint-användarkontot. Denna hemlighet måste skapas i Key Vault och konfigureras i din tjänstemiljö. Värdet är värdet för **ID för program (klient)** från [Konfigurera SharePoint-anslutning](e-invoicing-create-sharepoint-connection.md). |
    | Programhemlighet    | Ange namnet på den Key Vault-hemlighet som innehåller lösenordet till SharePoint-användarkontot. Värdet är värdet för **Hemlighet för programregistrering** från [Konfigurera SharePoint-anslutning](e-invoicing-create-sharepoint-connection.md). |
    | Webbplatsens namn             | Ange namnet på SharePoint-webbplatsen. |
    | Dokumentbiblioteksnamn | Ange namnet på SharePoint-dokumentbiblioteket. |
    | Tidsgräns               | Ange den maximala tidsgräns i millisekunder (ms) som systemet ska vänta på ett svar. Standardvärdet är 10 000 ms (10 sekunder). |
    | Huvudmapp           | Ange källan för filimporten eller mappen som tjänsten ska bearbeta filer från. |
    | Arkivmapp        | Ange mappen där bearbetade filer ska lagras. |
    | Mappfel          | Ange den mapp dit systemet ska flytta filer till om bearbetningen misslyckas. |
    | Maximal filstorlek         | Ange den maximala storleken, i byte, för en enda fil som bearbetas. Standardvärdet är 20 000 000 byte. |
    | Maximalt antal filer      | Ange det maximala antal filer som ska bearbetas för en enda åtgärd. Om du inte vill begränsa antalet filer ställer du in värdet på **0** (noll). |
    | Filfilter           | Ange en sträng för att filtrera efter filnamn. Det här fältet är valfritt. En enkel mask såsom **\*smth\*.ext** stöds, där varje asterisk (\*) representerar noll eller fler förekomster av något tecken. Du kan till exempel ange **\*.pdf** för att konfigurera kanalen så att den läser PDF-filer. |
    | Anpassat filnamn      | Ange anpassat filnamn från klienten. |

10. På fliken **Tillämplighetsregler** kan du granska och uppdatera kriterierna efter behov. Värdet i fältet **Kanal** måste vara lika med värdet som du angav i fältet **Datakanal** i föregående steg.
11. Markera **Spara** och stäng sedan sidan.
