---
title: Batchnummer rensas när ett nytt parti-ID väljs
description: När du granskar en plocklistejournalrad rensas värdet i fältet Batchnummer om du väljer ett nytt värde i fältet Parti-ID.
author: johanhoffmann
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ProdJournalTransBOM
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: datra
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 71977a04adb066a8b51c9bf7b8c5a4e752ca902e
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026900"
---
# <a name="batch-number-is-cleared-when-a-new-lot-id-is-selected"></a>Batchnummer rensas när ett nytt parti-ID väljs

KB-nummer: 4613107

## <a name="symptoms"></a>Symtom

När du granskar en plocklistejournalrad rensas värdet i fältet **Batchnummer** om du väljer ett nytt värde i fältet **Parti-ID**.

## <a name="resolution"></a>Upplösning

Systemet beter sig som det är utformat. Om du ändrar parti-ID ändrar du artikelkontexten. Därför återställs batchnumret.

Om du vill associera batchnumret med ett parti-ID måste du först ange parti-ID.
