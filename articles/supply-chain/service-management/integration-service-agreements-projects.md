---
title: Integration för serviceavtal och projekt
description: När du arbetar med serviceavtal och serviceavtalsrader, använder du data som konfigurerats i följande områden av avsnittet Projekthantering och redovisning.
author: sorenva
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProjParameters
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7252de08b40aa0668d3ce801b4cbd6f3a53ef12f
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/03/2022
ms.locfileid: "8673590"
---
# <a name="integration-for-service-agreements-and-projects"></a>Integration för serviceavtal och projekt 

[!include [banner](../includes/banner.md)]


När du arbetar med serviceavtal och serviceavtalsrader, använder du data som konfigurerats i följande områden i **Projekthantering och redovisning**.

## <a name="project-prices"></a>Projektpriser

Kostnaden och försäljningspriset för en serviceavtalstransaktion härleds från den inställning av självkostnad som gäller för projektet som är kopplat till serviceavtalet. Kostnad och försäljningspris kan konfigureras per projekt, medarbetare och kategori. 

## <a name="project-validation"></a>Projektvalidering

De projekt, medarbetare och kategorier som är tillgängliga för urval på en serviceavtalsrad kan begränsas via valideringskonfigureringen i **Projekthantering och redovisning**. Med valideringskonfigureringen kan du kombinera medarbetare, projekt och kategorier och därigenom styra åtkomsten. 

## <a name="project-line-properties"></a>Radegenskaper för projekt

En radegenskap registreras automatiskt för en serviceavtalsrad.

Radegenskaper skapas i formuläret **Radegenskaper** i **projekthantering och redovisning**. Den radegenskap som registreras i ett serviceavtal kopplas till det projekt som valts för serviceavtalet och senare ärvs av serviceavtalsraden. 

## <a name="default-offset-accounts"></a>Standardmotkonton

Om du anger en utgiftstransaktion markeras ett standardmotkonto automatiskt för transaktionen. Standardmotkontot konfigureras i projektet som är kopplat till det aktuella serviceavtalet.

## <a name="project-categories"></a>Projektkategorier

De kategorier som är tillgängliga för serviceavtalsrader konfigureras i formuläret **Projektkategorier** i **Projekthantering och redovisning**. 

> [!NOTE]
> <P>Kategorier som har kryssrutan <STRONG>Aktiv i journaler</STRONG> markerad på fliken <STRONG>projekt</STRONG> i formuläret <STRONG>projektkategorier</STRONG> kan väljas. Men om kryssrutan <STRONG>inaktiva kategorier</STRONG> är markerad på fliken <STRONG>journaler</STRONG> i formuläret <STRONG>projekthantering och redovisningsparametrar</STRONG> kan alla kategorier kan väljas.</P>

## <a name="project-parameters"></a>Projektparametrar

Om fältet **avslutade arbetare** på fliken **journaler** i formuläret **projekthantering och redovisningsparametrar** markeras kan du välja inaktiva medarbetare och aktiva medarbetare i formuläret **Serviceavtal** och **serviceorder**.

Du kan även aktivera fälten **Starttid** och **Sluttid** på fliken **Projekt** i formuläret **Serviceorder** för att ange start- och sluttider på serviceorderrader.

## <a name="enable-the-starting-and-ending-time-feature-for-service-orders"></a>Aktivera funktionen för start- och sluttid för serviceorder

1.  Klicka på **Projekthantering och redovisning** \> **Inställningar** \> **Parametrar för projekthantering och redovisning**.

2.  Klicka på fliken **journaler** och markera sedan kryssrutan **Visa start-/ sluttider**.

3.  Klicka på **Projekthantering och redovisning** \> **Inställning** \> **Journaler** \> **Journalnamn**.

4.  Markera journalnamnet som är kopplat till serviceordern.

5.  Klicka på fliken **Allmänt** och markera sedan kryssrutan **Visa start-/ sluttider**.


> [!NOTE]
> <P>Markera journalnamnet för serviceordern i fältet <STRONG>timme</STRONG> på fliken <STRONG>journaler</STRONG> i formuläret <STRONG>Serviceparametrar</STRONG>.</P>







[!INCLUDE[footer-include](../../includes/footer-banner.md)]