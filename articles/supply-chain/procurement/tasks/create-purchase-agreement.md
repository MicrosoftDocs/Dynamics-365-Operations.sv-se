---
title: Skapa ett nytt inköpsavtal
description: I den här avsnittet får du hjälp med att skapa ett inköpsavtal.
author: kamaybac
ms.date: 07/18/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchAgreement, PurchAgreementCreate, InventItemIdLookupSimple, AgreementConfirmRunForm, PurchAgreementHistory
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 19bfbe7bc78f08dbbc6f9924313749a46672e202
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5812336"
---
# <a name="create-a-purchase-agreement"></a>Skapa ett nytt inköpsavtal

[!include [banner](../../includes/banner.md)]

I den här avsnittet får du hjälp med att skapa ett inköpsavtal. Detta görs normalt av en inköpschef. Du kan använda den här proceduren i demonstrationsföretaget USMF eller på dina egna data. Du måste ha ställt in klassificeringar av inköpsavtal innan du börjar. När du har skapat ett avtal kan du använda det när du skapar en IO. Villkoren för inköpsavtalet kopieras då till huvudet och till alla rader i den ordning som påverkas av avtalet.


## <a name="create-a-new-purchase-agreement"></a>Skapa ett nytt inköpsavtal
1. Gå till **Navigeringsfönster > Moduler > Anskaffning och källa > Inköpsavtal > Inköpsavtal**.
2. Klicka på **Ny**.
3. I fältet **Leverantörskonto** väljer du den nedrullningsbara menyn och välj raden för önskad post.
4. I fältet **Klassificering av inköpsavtal** väljer du den nedrullningsbara menyn och välj raden för önskad post.
5. Expandera **Allmänt** snabbflik.
6. Ange ett datum i fältet **Utgångsdatum**.

    - Det här utgångsdatumet ska vara standard för alla utfästelserader och bestämmer hur länge varje specifik utfästelse är giltig.  

7. Ange ett namn på inköpsavtalet i fältet **Dokumenttitel**.

    - Lämna fältet **Standardutfästelse** angett till **Utfästelse för produktkvantitet** (eller ändra det om det inte är inställt på denna).  
    - Standardutfästelsevärdet bestämmer alternativen på avtalsraderna. Om du behöver en ny utfästelsetyp när du skapar avtalsraderna måste du ändra standardutfästelsen i rubriken. Det finns fyra typer av utfästelser: **Produktkvantitetsutfästelse** - för en viss kvantitet av en produkt; **Produktvärdeutfästelse** - för ett visst valutabelopp av en produkt; **Värdeutfästelse för produktkategori** - för ett visst valutabelopp i en anskaffningskategori där beloppet kan användas för en katalogartikel eller en artikel som inte finns i någon katalog; **Värdeutfästelse** - för ett visst valutabelopp som kan uppfyllas av vilken produkt som helst eller med valfri anskaffningskategori.  

8. Välj **OK**.

## <a name="add-a-commitment"></a>Lägg till en utfästelse
1. Välj **Markera rad**.
2. I fältet **Artikelnummer** välj önskad post i den nedrullningsbara menyn.
3. Ange ett nummer i fältet **Kvantitet**. Detta är den totala kvantitet som du har avtalat att köpa från leverantören.  
4. Ange ett tal i fältet **Enhetspris**.
5. Visa avsnittet **Raddetaljer**.
6. Ställ in alternativet **Max framtvingas** till **Ja**. Alternativet **Max framtvingas** begränsar användningen av utfästelsen. Du kan bara köpa upp till den kvantitet som har angetts i fältet **Kvantitet** för raden.  

## <a name="add-header-conditions"></a>Lägg till huvudvillkor
1. Välj **Alternativ** i åtgärdsfönstret.
2. Välj **Byt visning**.
3. Välj **Huvudvy**.
4. Expandera avsnittet **Villkor**.
5. I fältet **Betalningsmetod** väljer du önskad post i den nedrullningsbara menyn. Betalningsvillkoren från leverantörskontot visas här som standard.  
6. I fältet **Leveranssätt** väljer du önskad post i den nedrullningsbara menyn.
7. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Leveransvillkor**.

## <a name="confirm-and-activate-the-agreement"></a>Bekräfta och aktivera avtalet
1. Klicka på **Inköpsavtal** i åtgärdsfönstret.
2. VäljSelect **Bekräftelse**. Ange alternativet **Markera avtal som giltigt** till **Ja**.  
3. Välj **OK**.
4. Klicka på **Inköpsavtal** i åtgärdsfönstret.
5. Välj **Bekräftelser av inköpsavtal**. Med alternativet **Förhandsgranska/Skriv ut** kan du generera ett dokument för inköpsavtalet som du sedan kan skriva ut eller skicka till leverantören. Om du uppdaterar avtalet senare och bekräftar det på nytt visas båda versionerna här.  
6. Stäng sidan.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]