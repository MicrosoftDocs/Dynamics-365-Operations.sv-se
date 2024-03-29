---
title: Skapa länkar från Personal till en annan miljö
description: I den här artikeln beskrivs hur du skapar en länk från Microsoft Dynamics 365 Human Resources till en annan Dynamics 365-miljö.
author: twheeloc
ms.date: 03/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2021-29-11
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9640f460ed7b0b1a0cfdffb7c318bf833f8627fc
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9065320"
---
# <a name="create-links-from-human-resources-to-another-finance-environment"></a>Skapa länkar från Personal till en annan Finance-miljö

En kund kan ha två Dynamics 365-miljöer som de arbetar i. Kunden kanske till exempel har en Dynamics 365 Human Resources-miljö för Finance-infrastrukturen och behöver ansluta till en annan Dynamics 365 Finance-miljö. 

Med den här funktionen tillåts länkar från en Personal-sida till en specifik sida i en annan Finance-miljö. När länkarna har konfigurerats kan du ange var länken ska vara tillgänglig under Personal och på målsidan som ska öppnas i den andra miljön.

> [!Note] 
> Du måste aktivera **Förbättringar av användarupplevelse för personal** i **Funktionshantering** för att få funktionen.

## <a name="configure-target-systems"></a>Konfigurera målsystem

I Personal kan systemadministratörer definiera länkar som ska visas på **Personal**-sidor. Delar av konfigurationen är Finance-miljöer som du vill navigera till som mål för länken. 

Konfigurera målsystemet:
1. På sidan **Konfigurera länkar** väljer du **Konfigurera målsystemet**.  
2. Ge målsystemet ett namn och ange URL-adressen till Finance-miljön. När du har konfigurerat dina målsystem kan du definiera dina länkar.

## <a name="configure-links"></a>Konfigurera länkar

Varje länk som du skapar måste ha följande information definierad:
 - **Länk**: Namnet på länken. Används endast för identifiering.
 - **Aktivera den här länken**: Ställ in på **Ja** om du vill visa länken för användare av Personal.
 - **Visningsnamn**: Ange namnet som ska visas som en länk till den andra miljön. 
 - **Länk i formuläret**: Välj vilken sida du vill visa länken på. Länkar kan bara visas på arbetsytan **Självbetjäning för medarbetare** och sidorna **Jobb**, **Befattning**, **Arbetare** och **Strömlinjeformad arbetare**.
 - **Grupp**: Du kan organisera länkarna i grupper. Välj en befintlig grupp eller skapa en ny med kolumnen **Grupp**.
 - **Målsystem**: Välj det målsystem som skapades med **Konfigurera målsystemet**. Detta är den sekundära miljön som kommer att användas vid navigering med hjälp av länken.
 - **Använd användarens aktuella företag**: Välj **Ja** om du vill använda användarens nuvarande företag när du navigerar till Finance. Välj **Nej** för att välja det företag som ska användas.
 - Menyalternativet **Mål**: ange menyalternativet från Finance-miljön som länken ska användas för att navigera. Menyalternativ som du kan navigera direkt till är tillgängliga. 

   Så här hittar du det menyalternativ som krävs:
   1. Gå till Finance-miljön och öppna den sida som är målet för navigeringen. 
   2. Kopiera menyalternativet från URL:en. Om du till exempel vill att länken ska ta dig till medarbetarlistan i Ekonomi och drift anger du värdet som visas efter ”&mi” i URL-adressen. 
   3. Menyalternativet för att navigera till listsidan för medarbetare i det här exemplet är: HcmWorkerListPage_Employees.

 - **Länka till datakälla**: Välj den källa för data som länken refererar till. De vanligaste datakällorna såsom **arbetare** och **befattning** är tillgängliga.

### <a name="access-to-links"></a>Tillgång till länkar

Systemadministratörer vill se de nyligen skapta länkarna på de definierade sidorna även om alternativet **aktivera den här länken** är inställt på **Nej**. Detta kan användas för att testa länkar innan du visar dem för andra medarbetare. Andra roller visar endast de konfigurerade länkarna när alternativet **Aktivera den här länken** är inställd på **Ja**. Medarbetare som har åtkomst till de sidor där länkarna exponeras kommer att ha åtkomst till länken.

Användarna måste också ha säkerhetsbehörigheter i den sekundära miljön definierade för åtkomst till sidorna i den miljön. Om inte visas en dialogruta för säkerhet när du använder länken.


