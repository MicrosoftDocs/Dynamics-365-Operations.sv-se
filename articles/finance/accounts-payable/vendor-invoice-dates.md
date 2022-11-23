---
title: Datum för leverantörsfaktura
description: I den här artikeln beskrivs de datum som visas på leverantörsfakturor. Den förklarar också hur du automatiskt justerar bokföringsdatumet.
author: sunfzam
ms.date: 2/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2021-08-30
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 022fd0ce07fbb4c54afcf7334c1c9411e01dcf26
ms.sourcegitcommit: 9740f9b41a7dcf1821c6baccb2e05b9865ac2966
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/15/2022
ms.locfileid: "9775283"
---
# <a name="vendor-invoice-dates"></a>Datum för leverantörsfaktura

[!include [banner](../includes/banner.md)]

I den här artikeln beskrivs de datum som visas på leverantörsfakturor. Den förklarar också hur du automatiskt justerar bokföringsdatumet.

På sidan **Pågående leverantörsfaktura detaljerad** på fakturahuvudet visar fyra datum: **mottagningsdatum för faktura**, **fakturadatum**, **bokföringsdatum** och **förfallodatum**. När en leverantörsfaktura skapas anges följande datum som standard:

- **Mottaget fakturadatum** – Det här fältet ställs in på aktuellt systemdatum.
- **Bokföringsdatum** – Det här fältet ställs in på aktuellt systemdatum. 
- **Förfallodatum** – Datumet i det här fältet beräknas utifrån bokföringsdatumet och betalningsvillkoren.
- **Fakturadatum** – Som standard är det här fältet tomt. Du kan dock ange värdet som du vill. I så fall datumet i fältet **Förfallodatum** räknas om utifrån fakturadatum och betalningsvillkoren.

Ibland kan en leverantörsfaktura vara i pågående läge under en lång tid efter periodslutet. När den är klar för bokföring används fortfarande det gamla bokföringsdatumet för den tidigare bokföringsperioden. Den perioden har nu dock stängts. Därför måste en leverantörsreskontraansvarig (AP) manuellt ändra alla bokföringsdatum till den nya bokföringsperioden för alla pågående fakturor som tidigare har skapats.

Med hjälp av funktionen som beskrivs i den här artikeln kan du justera bokföringsdatumet automatiskt enligt verksamhetens krav.

## <a name="parameter-for-automatically-adjusting-the-vendor-invoice-posting-date"></a>Parameter för automatisk justering av bokföringsdatum för leverantörsfaktura

Följ dessa steg om du vill automatiskt justera bokföringsdatum för leverantörsfakturor.

1.  Gå till **Leverantörsreskontra \> Inställningar \> Parametrar för leverantörsreskontra**.
2.  På fliken **Redovisning och moms** på fältet **Justera bokföringsdatum automatiskt**, välj ett av följande värden:

    - **Ingen ändring** – Systemet ändrar inte bokföringsdatumet automatiskt vid bokföringen. Detta värde är valt som standard.
    - **Ändra alltid bokföringsdatum till systemdatum** – Bokföringsdatumet ändras automatiskt till systemdatumet vid bokföring.
    - **Ändra bokföringsdatum till systemdatum när bokföringens datumperiod är stängd eller spärrad** – Bokföringsdatumet ändras automatiskt till systemdatum under bokföring, men endast om motsvarande period för bokföringsdatum har statusen **Stängd** eller **Spärrad**.
    - **Ändra bokföringsdatum till första dagen av den nya perioden när bokföringens datumperiod är stängd eller spärrad** – bokföringsdatum ändras till den första dagen av den nya öppna perioden, men endast om motsvarande period för bokföringsdatum har statusen **Stängd** eller **Spärrad**.

> [!NOTE]
> Om det nya bokföringsdatumet som justerades automatiskt är i ett nytt räkenskapsår, uppdateras inte bokföringsdatumet för fakturan. Användaren får ett felmeddelande "Räkenskapsåret har ändrats. Kontrollera och ange bokföringsdatumet på samma sätt." Datumet för fakturans bokföring måste uppdateras till det nya räkenskapsåret för att det ska gå att bokföra.

## <a name="impact-of-posting-date-changes"></a>Inverkan på ändringar av bokföringsdatum

När bokföringsdatumet på en pågående leverantörsfaktura ändras, påverkar ändringen följande:

- **Förfallodatum**

    - Om fältet **Fakturadatum** är tom, beräknas förfallodatumet om baserat på det nya bokföringsdatumet och betalningsvillkoren.
    - Om fältet **Fakturadatum** tidigare ställts in påverkas inte förfallodatumet av ändringen av bokföringsdatumet.

- **Kassarabattdatum**

    - Om fältet **Fakturadatum** är tomt används det nya bokföringsdatumet för att beräkna kassarabatten.
    - Om fältet **Fakturadatum** tidigare ställts in ändras inte kassarabatten.

- **Valutakurs** – Valutakursdatumet bestäms av inställningen av alternativet **Uppdatera leverantörsredovisning med fakturadatum** på fliken **Faktura** på sidan **Parametrar för leverantörsreskontra** (**Leverantörsreskontra \> Inställningar \> Parametrar för leverantörsreskontra**).

    - Om detta alternativ är inställt på **Ja**, används **fakturadatumet** och ändringen av **bokföringsdatum** påverkar inte valutakursen.
    - Om det här alternativet ställs in på **Nej** används bokföringsdatumet för att beräkna valutakursen. När bokföringsdatumet uppdateras omberäknas redovisnings- och rapporteringsbeloppen. Därför måste matchningsvalidering göras igen.

## <a name="validation"></a>Validering

Två andra fält på fliken **Faktura** på sidan **Parametrar för leverantörsreskontra** (**Leverantörsreskontra \> Inställningar \> Parametrar för leverantörsreskontra**) påverkar bearbetning av fakturor:

- Om fältet **Kontrollera använt fakturanummer** anges till **Avvisa dubbletter inom räkenskapsåret** används bokföringsdatumet för att kontrollera om det finns dubbletter av fakturor vid fakturabokföring.
- Om fältet **Kräv dokumentdatum på leverantörsfaktura** anges till **Felalternativ**, krävs fältet **Fakturadatum på väntande fakturahuvud**. Om fakturadatumet är senare än bokföringsdatumet visas ett felmeddelande.
