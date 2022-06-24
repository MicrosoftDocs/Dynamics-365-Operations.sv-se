---
title: Det går inte att fastställa momskod
description: I det här ämnet beskriver hur du felsöker felet "Momskod kan inte bestämmas" i beräkningstjänsten för moms.
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
ms.openlocfilehash: 6a74724de38cf362900277ab9addc8e6894f7689
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8877871"
---
# <a name="tax-code-cannot-be-determined"></a>Det går inte att fastställa momskod

[!include [banner](../includes/banner.md)]

Den här artikeln förklarar de felsökningssteg som du kan vidta om du får en "Momskod kan inte bestämmas" i beräkningstjänsten för moms.

## <a name="symptom"></a>Symptom

Du får följande felmeddelande: "Rubrik/rader - 1, momskod kan inte fastställas." Du kan också hitta felet i felsökningsfilen, på det sätt som visas i följande exempel. Mer information finns i [Aktivera felsökningsläget för att felsöka problem](tcs-troubleshooting-enable-debug-mode.md).

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
                                "Code": "TaxSetup20001",
                                "Message": "Header/Lines - 1, tax code cannot be determined."
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

Problemet uppstår troligen eftersom momsgruppen och artikelmomsgruppen inte är sammanlänkade.

## <a name="troubleshoot"></a>Felsök

Följ stegen nedan för att felsöka problemet.

1. Kontrollera i felsökningsfilen att momsgruppen och artikelmomsgruppen har fastställts. Om värdena för **Momsgrupp** och **Artikelmomsgrupp** är tomma har momsgruppen och artikelskattegruppen inte bestämts. Om de har fastställts kan resultatet bli fel.

    Här är ett exempel på en felsökningsfil.

    ```json
    ======================Tax service calculation result JSON:===========================
    {
        "taxDocument": {
            "Header": [
                {
                    "Lines": [
                        {
                            "Tax Codes": {},
                            "Measures": {
                                "Tax Group": "Group A",
                                "Item Tax Group": "Group B"
                            },
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

2. Kontrollera att alternativet **Åsidosätt moms** på fliken **Inställningar** för raddetaljerna för försäljningsordern har aktiverats.

    - Om den är aktiverad bestäms momskoderna av värdena för **Momsgrupp** och **Artikelmomsgrupp** som du anger på transaktionsraden. Kontrollera att de här värdena har angetts på rätt sätt.
    - Om den inte är aktiverad ska du kontrollera att korrekta värden har ställts in för fälten **Tillämplighet för momsgrupp** och **Tillämplighet för artikelmomsgrupp**. Mer information finns i [Inget matchande resultat hittas](tcs-troubleshooting-no-matching-result.md).

3. Om momsgruppen och artikelmomsgruppen har fastställts på rätt sätt, ska du avgöra om det finns någon skärningspunkt för dem.

    1. I RCS, gå till **Momsfunktioner** \> **Momskoder och grupper** \> **Momsgrupp**.

        | Radmomsgrupp | Momskoder |
        |----------------|-----------|
        | Grupp A        | A         |

    2. Gå till **Momsfunktioner** \> **Momskoder och grupper** \> **Artikelmomsgrupp**.

        | Line.Item momsgrupp | Momskoder |
        |---------------------|-----------|
        | Grupp B             | B         |

    Om det inte finns någon skärningspunkt för momsgruppen och artikelmomsgruppen, bestäms inte momskoden.

## <a name="mitigation"></a>Minskning

1. Gå igenom varje steg i avsnittet [Felsöka](#troubleshoot) i den här artikeln och korrigera inställningarna efter behov. Om momsgruppen och artikelmomsgruppen inte har fastställts korrekt, finns det [inget matchningsresultat att hitta](tcs-troubleshooting-no-matching-result.md).
2. Om det inte finns någon skärningspunkt för momsgruppen och artikelmomsgruppen, skapa en ny funktionsversion i RCS och korrigera inställningen.

    - Gå till **Momsfunktioner** \> **Momskoder och grupper** > **Artikelmomsgrupp**.

        | Line.Item momsgrupp | Momskoder |
        |---------------------|-----------|
        | Grupp B             | A;B       |

    Momskoden bestäms som **A**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
