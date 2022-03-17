---
title: Konfigurera en SharePoint-anslutning
description: I detta ämne beskrivs hur du konfigurerar en anslutning så att e-fakturering får åtkomst till en Microsoft SharePoint-webbplats.
author: dkalyuzh
ms.date: 12/15/2021
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
ms.openlocfilehash: 6b9fffc1f3525e69792517dd1c6ebdcfbe5a74d2
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/02/2022
ms.locfileid: "8371726"
---
# <a name="configure-a-sharepoint-connection"></a>Konfigurera en SharePoint-anslutning

[!include [banner](../includes/banner.md)]

Den e-faktureringstjänsten kan läsa filer från Microsofts SharePoint-mappar och överföra filer till SharePoint. Om du vill säkerställa att e-fakturering har åtkomst till en specifik SharePoint-webbplats måste du ange autentiseringsuppgifter för webbplatsen till e-faktureringstjänsten. För att säkerställa att autentiseringsuppgifterna lagras på ett säkert sätt bör du dessutom inte ange dem direkt. Lagra dem istället i ett Azure-nyckelvalv, och tillhandahåll en hemlighet för Azure Key Vault.

## <a name="grant-access-to-a-sharepoint-folder"></a>Bevilja åtkomst till en SharePoint-mapp

1. Skapa en programregistrering i den klientorganisation där Regulatory Configuration Service (RCS) har installerats.

    1. Logga in på [Azure-portal](https://portal.azure.com/).
    2. Gå till **Appregistreringar**.
    3. Välj **Ny registrering**.
    4. Ange ett namn, till exempel **SharePoint-app för e-fakturering** och slutför registreringen
    5. Välj den nya programregistreringen.
    6. På fliken **Autentisering** aktiverar du alternativet **Tillåt offentliga klientflöden**.
    4. På fliken **Certifikat och hemligheter** väljer du **Ny klienthemlighet** för att skapa en klienthemlighet.
    5. Kopiera värdet för den hemlighet som skapades.

    Följ dessa steg:

    - Använd inte samma programregistrering för olika tjänster.
    - Följ [rekommendationerna för lösenordspolicy](/microsoft-365/admin/misc/password-policy-recommendations?view=o365-worldwide).
    - Ställ in lösenordsrotation. Under rotationen skapar du en ny klienthemlighet för programregistreringen, uppdaterar nyckelvalet och tar sedan bort den gamla hemligheten.

2. Spara värdena för **Hemlighet för programregistrering** och **ID för program (klient)** som två nya hemligheter i nyckelvalvet bland inställningarna för din e-faktureringsmiljö.
3. I fältet miljö anger du namnet på tilläggsmiljön för e-fakturering som du skapade under installationen av RCS.
4. I Azure-portalen beviljar du åtkomst till SharePoint. Det här steget ska utföras av klientorganisationens administratör.

    1. Välj den programregistrering som du själv har skapat.
    2. På fliken **API-behörigheter** väljer du **Lägg till behörighet**.
    3. Välj **Microsoft-diagram (programbehörigheter)** \> **Webbplatser.Markerade**.
    4. Välj **Bevilja administratörsmedgivande för \<user&nbsp;name\>**.
    5. Granska fältet **Status** för att se till att behörigheterna beviljas.

        ![Behörigheter som beviljats på fliken för API-behörigheter.](media/configured-permissions.jpg)

    6. Öppna [Graph Explorer – Microsoft Graph](https://developer.microsoft.com/graph/graph-explorer) och logga in.
    7. I vänstra fönstret, på fliken **Exempelfrågor**, under **SharePoint-webbplatser**, väljer du **hämta SharePoint-webbplats baserat på webbplatsen relativa sökväg**.
    8. Fyll i parametrarna för **\{värdnamn\}** och **\{serverrelativ sökväg\}**. Fyll till exempel i `<domain>.sharepoint.com` för **\{värdnamn\}** och `sites/<siteName>` för **\{serverrelativ sökväg\}**.

        > [!NOTE]
        > Lämna parametern **\{serverrelativ sökväg\}** för standardwebbplatsen tom.

    9. Välj **Kör fråga** och spara resultatet.
    10. Konfigurera följande fråga.

        `POST https://graph.microsoft.com/v1.0/sites/{site-id}/permissions`

        I den här frågan är **\{webbplats-ID\}** värdet på **ID**-noden från föregående frågesvar.

        Här är begärandetexten.

        ```json
        {
            "roles": [
                "read",
                "write"
            ],
            "grantedToIdentities": [
                {
                    "application": {
                        "id": "{app-id}",
                        "displayName": "{app-name}"
                    }
                }
            ]
        }
        ```

        I denna begäran är **\{app-ID\}** lika med värdet **ID för program (klient)** och **\{appnamnet\}** är värdet **Programnamn**.

        ![POST-fråga.](media/app-id-query.jpg)

    11. På fliken **Ändra behörighetet** väljer du **Öppna behörighetspanelen** och sedan **Webbplatser** \> **Sites.FullControl.All** \> **Medgivande**.
    12. Välj **Kör fråga**.

E-faktureringstjänsten har nu åtkomst till din SharePoint-webbplats.
