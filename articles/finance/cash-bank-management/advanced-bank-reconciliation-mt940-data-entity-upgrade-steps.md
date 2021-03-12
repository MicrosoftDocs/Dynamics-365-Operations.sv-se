---
title: Avancerad MT940-import för bankavstämning – uppgradering för sammansatt dataenhet
description: Ett sekvensnummer måste läggas till bankutdragimportenheten för att stödja MT940-formatet.
author: panolte
manager: AnnBe
ms.date: 06/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer
ms.reviewer: roschlom
ms.custom: 221594
ms.assetid: dddc99ae-56ae-48df-856a-131079c17dcb
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 4d3bd54f0f2329c8c0602171a7f3c1ca444672b3
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4985421"
---
# <a name="advanced-bank-reconciliation-mt940-import--composite-data-entity-upgrade"></a>Avancerad MT940-import för bankavstämning – uppgradering för sammansatt dataenhet

[!include [banner](../includes/banner.md)]

Ett sekvensnummer måste läggas till bankutdragimportenheten för att stödja MT940-formatet. 

Använd följande steg när du vill lägga till bankutdragimportenheten för att stödja MT940-formatet.

1.  Kompilera och synkronisera följande:
    -   Sammansatt enhet\\BankStatementImportEntity
    -   Enhet\\BankStatementBalanceEntity
    -   Enhet\\BankStatementDocumentEntity
    -   Enhet\\BankStatementEntity
    -   ENhet\\BankStatementLineEntity
    -   Register\\BankStatementStaging

2.  Datahantering\\dataprojekt.
    1.  Läs in MT940-importprojekt
        1.  Ändra XSLT.
            -   Klicka på **Visa karta**.
            -   Klicka på **Visa karta** på bankutdragsdokumentet.
            -   Klicka på **Transformeringar**
            -   Ta bort filen BankReconiliation-to-Composite.xslt.
            -   Lägg till den nya versionen av BankReconiliation-to-Composite.xsl.

        2.  Visa layouten **Löpnummer** på **Källdata**.
            1.  Källdataformat = XML-Element.
            2.  Enhetsnamn = Bankutdrag.
            3.  Överföra datafil = ny version SampleBankCompositeEntity.xml.
            4.  Klicka på **Ja** om du vill skriva över den befintliga filen.
            5.  Klicka på **Ja** om du vill generera en ny mappning.
            6.  Kontrollera att S **equenceNumber** mappas.
                -   Klicka på **Visa karta** på bankutdraget.
                -   Kontrollera att **SequenceNumber** mappas från Källa till Mellanlagring.

3.  Importera det nya utdraget.




