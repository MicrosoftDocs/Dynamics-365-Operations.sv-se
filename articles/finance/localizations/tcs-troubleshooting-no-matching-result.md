---
title: Det gick inte att hitta matchande resultat
description: I det här ämnet beskriver hur du felsöker felet "Inga matchande resultat inte hittades" i beräkningstjänsten för moms.
author: hangwan
ms.date: 03/25/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxIntegrationTaxServiceParameters
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: hangwan
ms.search.validFrom: 03/23/2022
ms.dyn365.ops.version: Version 10.0.21
ms.openlocfilehash: d3bbc76741fdd018d1b2987538b8de7f6d92ee53
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8845156"
---
# <a name="no-matching-result-could-be-found"></a>Det gick inte att hitta matchande resultat

[!include [banner](../includes/banner.md)]

Den här artikeln förklarar de felsökningssteg som du kan vidta om du får en "Inga matchande resultat inte hittades" i beräkningstjänsten för moms.

## <a name="symptom"></a>Symptom

Du får följande felmeddelande: "Rubrik/rader - 1, Momsgrupp, inga matchningsresultat kunde hittas."

```json
======================Tax service calculation result JSON:===========================
{
    "taxDocument": {
        "Header": [
            {
                "Lines": [
                    {
                        ...
                        "Errors": [
                            {
                                "Code": "TaxSetup20000",
                                "Message": "Header/Lines - 1, Tax group applicability, no matching result could be found."
                            }
                        ],
                        "Adjustment": null
                    }
                ],
                "Measures": {
                    ...
                },
                ...
            }
        ]
    },
    ...
}
```

## <a name="cause"></a>Orsak

Problemet uppstår när funktionsinställningarna i Regulatory Configuration Service (RCS) är fel.

## <a name="troubleshoot"></a>Felsök

1. Hämta felsökningsfilen. Mer information finns i [Aktivera felsökningsläget för att felsöka problem](tcs-troubleshooting-enable-debug-mode.md).
2. Jämför beräkningsindata för momstjänst med funktionsinställningarna för att korrigera inställningsproblemet.

    Följande exempel visar beräkningsindata för Momstjänst.

    ```json
    ===============================Tax service calculation input JSON:=====================================
    {
        "TaxableDocument": {
            "Header": [
                {
                    "Lines": [
                        {
                            ...
                        }
                    ],
                    "Business Process": "Sales",
                    "Ship From Zip Code": "30159",
                }
            ]
        },
        "Parameter": {
            ...
        },
        "Adjustment": {
            "Lines": {}
        }
    }
    ```

    I följande tabell visas tillämpligheten för momsgruppen i RCS.

    | Header.Business-process | Lines.Business enhet | Header.Ship från postnummer | Momsgrupp |
    |-------------------------|---------------------|---------------------------|-----------|
    | Journal                 |                     |                           | Grupp A   |
    | Försäljning                   |                     | 30160                     | Grupp B   |

    Enligt beräkningsindata för momstjänst kommer värdet **Affärsprocess** i rubriken vara **Försäljning** och **Leverera från postnummer** på rubriken **30159**. Den här inmatningen baseras på inställningen av tillämplighetsregler i RCS. Eftersom det inte finns någon matchande rad, inträffar felet.

    > [!NOTE]
    > Om värdet i tillämplighetsregeln är tomt kan regeln användas för alla värden.

## <a name="mitigation"></a>Minskning

Följ dessa steg för att lindra felet.

1. I RCS, gå till **Globaliseringsfunktioner** \> **Momsberäkning**.
2. Skapa en ny version av funktionen.
3. Lägg till en rad för motsvarande information.

    | Header.Business-process | Lines.Business enhet | Header.Ship från postnummer| Momsgrupp |
    |-------------------------|---------------------|--------------------------|-----------|
    | Journal                 |                     |                          | Grupp A   |
    | Försäljning                   |                     | 30160                    | Grupp B   |
    | Försäljning                   |                     | 30159                    | Grupp B   |

4. Publicera versionen för funktionsinställningarna.
5. I Microsoft Dynamics 365 Finance, gå till **Moms** \> **Inställningar** \> **Momsinställning** \> **Parametrar för momsberäkning** och välj den nya versionen.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
