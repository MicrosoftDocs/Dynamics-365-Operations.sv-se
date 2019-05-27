---
title: Skapa ett nytt inköpsavtal
description: I den här proceduren får du hjälp med att skapa ett inköpsavtal.
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchAgreement, PurchAgreementCreate, InventItemIdLookupSimple, AgreementConfirmRunForm, PurchAgreementHistory
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b317f0a0fc8f198bad9501f325557ac2a4796989
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1547639"
---
# <a name="create-a-purchase-agreement"></a>Skapa ett nytt inköpsavtal

[!include [task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren får du hjälp med att skapa ett inköpsavtal. Detta görs normalt av en inköpschef. Du kan använda den här proceduren i demonstrationsföretaget USMF eller på dina egna data. Du måste ha ställt in klassificeringar av inköpsavtal innan du börjar. När du har skapat ett avtal kan du använda det när du skapar en IO. Villkoren för inköpsavtalet kopieras då till huvudet och till alla rader i den ordning som påverkas av avtalet.


## <a name="create-a-new-purchase-agreement"></a>Skapa ett nytt inköpsavtal
1. Gå till Anskaffning och källa > Inköpsavtal > Inköpsavtal.
2. Klicka på Ny.
3. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Leverantörskonto.
4. Hitta och markera önskad post i listan.
5. Klicka på länken på den valda raden i listan.
6. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Klassificering av inköpsavtal.
7. Hitta och markera önskad post i listan.
8. Klicka på länken på den valda raden i listan.
9. Expandera avsnittet Allmänt.
10. Ange ett datum i fältet Utgångsdatum.
    * Det här utgångsdatumet ska vara standard för alla utfästelserader och bestämmer hur länge varje specifik utfästelse är giltig.  
11. Ange ett namn på inköpsavtalet i fältet Dokumenttitel.
    * Lämna fältet Standardutfästelse angett till Utfästelse för produktkvantitet (eller ändra det om det inte är inställt på denna).  
    * Standardutfästelsevärdet bestämmer alternativen på avtalsraderna. Om du behöver en ny utfästelsetyp när du skapar avtalsraderna måste du ändra standardutfästelsen i rubriken.  Det finns 4 typer av utfästelser: Produktkvantitetsutfästelse - för en viss kvantitet av en produkt; Produktvärdeutfästelse - för ett visst valutabelopp av en produkt; Värdeutfästelse för produktkategori - för ett visst valutabelopp i en anskaffningskategori där beloppet kan användas för en katalogartikel eller en artikel som inte finns i någon katalog; Värdeutfästelse - för ett visst valutabelopp som kan uppfyllas av vilken produkt som helst eller med valfri anskaffningskategori.  
12. Klicka på OK.

## <a name="add-a-commitment"></a>Lägg till en utfästelse
1. Klicka på Lägg till rad.
2. Markera vald rad i listan.
3. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelnummer.
4. Välj den produkt som du vill lägga till en utfästelse för.
5. Klicka på länken på den valda raden i listan.
6. Ange ett tal i fältet Kvantitet.
    * Detta är den totala kvantitet som du har avtalat att köpa från leverantören.  
7. Ange ett tal i fältet Enhetspris.
8. Expandera avsnittet Radinformation.
9. Ställ in alternativet Max framtvingas till Ja.
    * Alternativet Max framtvingas begränsar användningen av utfästelsen. Du kan bara köpa upp till den kvantitet som har angetts i fältet Kvantitet för raden.  
10. Komprimera avsnittet Raddetalj.

## <a name="add-header-conditions"></a>Lägg till huvudvillkor
1. Klicka på Alternativ i åtgärdsfönstret.
2. Klicka på Ändra vy.
3. Klicka på Huvudvy.
4. Expandera villkorsavsnittet.
5. I fältet Betalningsmetod, öppna sökningen genom att klicka på den nedrullningsbara knappen.
    * Betalningsvillkoren från leverantörskontot visas här som standard.       
6. Hitta och markera önskad post i listan.
7. Klicka på länken på den valda raden i listan.
8. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Leveranssätt.
9. Klicka på länken på den valda raden i listan.
10. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Leveransvillkor.
11. Klicka på länken på den valda raden i listan.

## <a name="confirm-and-activate-the-agreement"></a>Bekräfta och aktivera avtalet
1. Klicka på Inköpsavtal i åtgärdsfönstret.
2. Klicka på Bekräftelse.
    * Ange alternativet Markera avtal som giltigt till Ja.  
3. Klicka på OK.
4. Klicka på Inköpsavtal i åtgärdsfönstret.
5. Klicka på Bekräftelser av inköpsavtal.
    * Med alternativet Förhandsgranska/Skriv ut kan du generera ett dokument för inköpsavtalet som du sedan kan skriva ut eller skicka till leverantören. Om du uppdaterar avtalet senare och bekräftar det på nytt visas båda versionerna här.  
6. Stäng sidan.

