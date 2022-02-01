---
title: Datum för leverantörens momsregistrering
description: I det här avsnittet finns information om en funktion för att aktivera datum för momsregistrering från leverantörer.
author: anasyash
ms.date: 01/15/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.custom: intro-internal
ms.search.region: global
ms.author: anasyash
ms.search.validFrom: 2022-01-15
ms.dyn365.ops.version: AX 10.0.24
ms.openlocfilehash: 882d5a8718d819cff80bfa5b86e054a39e9db159
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2022
ms.locfileid: "7992069"
---
# <a name="date-of-vendor-vat-register"></a>Datum för leverantörens momsregistrering

I Microsoft Dynamics 365 Finance version 10.0.24, ett nytt fält **Datum för leverantörens momsregistrering** är tillgängligt för leverantörsfakturor. I det här fältet anges datum för den momsbara leveransen för ett inköp.

Aktivera det nya fältet genom att gå till arbetsytan **funktionshantering** söka och välja **Aktivera datum för leverantörsmomsregistrering på leverantörsfakturor** och markera **Aktivera nu**.

Inkommande fakturor från dina leverantörer kan ha två datum: datumet när leverantören utfärdade fakturan och datumet för den momspliktiga leveransen (det vill säga det datum då leverantören debiterade momsen). I vissa fall kan dessa två datum skilja sig åt.

Du kan dra av det inkommande momsbeloppet för en inköpsfaktura och inkludera den fakturan i momsrapporter senare, på ett datum som skiljer sig från båda tidigare nämnda datum. Datumet styrs av lokala lagstiftningsregler för uppskjutet inkommande momsavdrag för vissa scenarier. Det varierar efter land eller region.

Vissa momsrapporter, till exempel [rapporten Momskontrollutdrag](emea-cze-vat-declaration-tax-declaration-model.md#vat-control-statement) i Tjeckien kräver att datumet för den momspliktiga leveransen rapporteras för ett inköpsdokument. Det här datumet måste rapporteras så att skattemyndigheten kan stämma av momsrapporteringen mellan motsvarande myndigheter.

I Finance kan du definiera datum i följande fält:

- **Fakturadatum** – Det datum då fakturan utfärdades av leverantören.
- **Momsregistreringsdatum** – Datumet för momsbeloppsavdraget för inköpsfakturan.
- **Momsregistreringsdatum för leverantör** – Datumet för leverantörens momspliktiga leverans.
- **Ta emot dokumentdatum** – Datumet när du tog emot fakturan.

Dessa fält finns på följande sidor:

- Leverantörsfaktura
- Leverantörsfakturaregister
- Godkännande av leverantörsfaktura
- Leverantörsfakturajournal

Efter att leverantörsfakturan har bokförts kan du granska datumen på sidorna **Fakturajournal** och **Leverantörstransaktioner**.
