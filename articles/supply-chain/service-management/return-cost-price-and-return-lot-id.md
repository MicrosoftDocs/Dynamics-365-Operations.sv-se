---
title: Retursjälvkostnad och returparti-ID
description: Vill du eventuellt att kostnaden för de returnerade produkterna lika med kostnaden för produkter som vid den tidpunkt då du sålde produkter till kunden. Det gör du med hjälp av **returparti-ID**.
author: ShylaThompson
ms.date: 04/30/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReturnTableListPage, ReturnInventTransIdLookup, ReturnItemNumLookup
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 86e048139da28c04c9f5ca03d71f92e5a7e60652
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5836000"
---
# <a name="return-cost-price-and-return-lot-id"></a>Retursjälvkostnad och returparti-ID        

[!include [banner](../includes/banner.md)]



Kostnaden för produkter som returneras till lagret beräknas med hjälp av den aktuella kostnaden för produkter. Vill du eventuellt att kostnaden för de returnerade produkterna lika med kostnaden för produkter som vid den tidpunkt då du sålde produkter till kunden. Det gör du med hjälp av fältet **returparti-ID** på snabbfliken **radinformation** i formuläret **försäljningsorder**.

Tänk på följande scenario: Du fakturerar en kund. Kunden returnerar sedan de levererade produkterna till dig. Du returnerar produkterna till lagret. I det här fallet när du krediterar kunden för returnerade produkter beräknas kostnaden för dessa produkter genom att använda den aktuella kostnaden för produkter. Men om du använder fältet **returparti-ID** beräknas kostnaden för de returnerade produkterna med hjälp av kostnaden på fakturan för den ursprungliga försäljningen till kunden.

Om du vill använda en annan kostnad än den aktuella kostnaden för returer för en kund använder du någon av följande metoder.

## <a name="method-1-manually-enter-the-return-cost-price"></a>Metod 1: Ange retursjälvkostnaden manuellt

Som standard när du lägger till objekt mot en returorder returneras artiklarna till lagret till den aktuella självkostnaden. Följ dessa steg om du vill ange en annan retursjälvkostnaden.

1.  Klicka på **Försäljning och marknadsföring** \> **Returorder** \> **Alla returorder** \> **Alla försäljningsorder**.

2.  I **åtgärdsrutan** i gruppen **Ny** klickar du på **Returorder**.

3.  I formuläret **Skapa returorder** välj ett kundkonto och klicka sedan på **OK**.

4.  I formuläret **returorder - RMA-nummer: %1, %2** välj ett objekt och ange en negativ kvantitet i fältet **kvantitet**.

5.  Klicka på **Radinformation**.

6.  På fliken **Allmänt** ange ett värde i fältet **Retursjälvkostnad**. Det här värdet används när varorna har returnerats till lagret. Om du inte anger ett värde, används det aktuella självkostnaden när varorna har returnerats till lagret.

## <a name="method-2-automatically-generate-the-cost-price-based-on-the-customer-invoice-line"></a>Metod 2: Generera automatiskt självkostnaden baserat på kundfakturarad

Detta är det bästa sättet att skapa returrader. Kostnaden för produkter som vid den tidpunkt då du sålde produkter till kunden, skapa en returorder och anger en försäljningsrad ska returneras.

1.  Klicka på **Försäljning och marknadsföring** \> **Returorder** \> **Alla returorder** \> **Alla försäljningsorder**.

2.  I **åtgärdsrutan** i gruppen **Ny** klickar du på **Returorder**.

3.  I formuläret **Skapa returorder** välj ett kundkonto och klicka sedan på **OK**.

4.  I formuläret **returorder - RMA-nummer: %1, %2** i **åtgärdsfönstret**, klickar du på **söka efter försäljningsorder**.

5.  I formuläret **söka efter försäljningsorder**, välj fakturaraden som returneras och klicka på **OK**.
    
    På snabbfliken **Radinformation** klickar du på fliken **allmänt** och fältet **returparti-ID** visar värdet från den ursprungliga försäljningsraden. Dessutom kan fältet **Retursjälvkostnad** visa kostnadsvärdet från den ursprungliga försäljningsraden.

## <a name="cost-calculation-example"></a>Exempel på kostnadsberäkning

När du använder fältet **returparti-ID** på en returorderrad för att ange retursjälvkostnaden, används kostnaden på returorderraden. Om du använder funktionen för lagerstängning eller omberäkning justeras kostnaden på den ursprungliga försäljningsraden. Kostnaden på returorderraden justeras automatiskt så att den avspeglar samma kostnad per styck.

1.  Skapa och släppa en produkt som heter Test. I formuläret **Information om frisläppt produkt** anger du följande information:
    
    1.  På fliken **hantera kostnader** i fältet **artikelgrupp** väljer du gruppen **delar**.
    
    2.  På snabbfliken **Allmänt** i fältet **Artikelmodellgrupp**, välj **DEF**.
    
    3.  På snabbfliken **Köp** i fältet **Pris** ange 10,00 som artikelns självkostnad.
    
    4.  I **Åtgärdsfönstret**, klicka på **Dimensionsgrupp**. I fältet **lagringsdimensionsgrupp** väljer du **Endast plats och lagerställe**. I fältet **spårningsdimensionsgrupp** väljer du **Inga aktiva spårningsdimensioner**.

2.  Skapa en inköpsorder för 10 delar av testartikel på 6,00 per styck och bokföra en faktura för inköpsordern.
    
    Skapa en andra inköpsorder för 10 delar av testartikel på 8,00 per styck och bokföra en faktura för inköpsordern.

3.  Bokföra en faktura för en försäljningsorder att sälja fem delar av testartikeln.
    
    I det här fallet kostade försäljningsorderraden 35,00 (5 enheter \*7,00 genomsnittlig kostnad per styck).

4.  Skapa en ny returorder för kunden. I formuläret **söka efter försäljningsorder**, välj fakturaraden och klicka på **OK**.

5.  I formuläret **returorder - RMA-nummer: %1, %2** kontrollerar du att en returorder skapas för att returnera testartikeln. Returorderns kvantiteten anges till -5,00.
    
    Fältet **returparti-ID** visar ett parti-ID. Detta parti-ID hämtas från den ursprungliga försäljningsordern för artikeln som har sålts till kunden. Dessutom kan fältet **Retursjälvkostnad** visa självkostnaden från den ursprungliga försäljningsraden.

6.  Registrera inleverans av returnerade artiklar.

7.  Bokför en följesedel för de returnerade artiklarna.

8.  Bokför en faktura för returordern. På listsidan **alla försäljningsorder**, välj en försäljningsorder för vilken ordertypen är **returnerad order**.

9.  Öppna formuläret **Lagertransaktioner** Kontrollera returen kostnadsberäknats till 7,00 per enhet med hjälp av värdet i fältet **Retursjälvkostnad** för totalt 35,00 i fältet **kostnadsbelopp**. Du kan öppna formuläret **lagertransaktioner** från formuläret **returorder - RMA-nummer: %1, %2**. Klicka på rutnätet **Rader**, klicka på **Lager** \> **Transaktioner**.

10. I Hantering av lager och lagerplatser använd formuläret **stängning och justering** när du vill köra proceduren **3. Stäng**.
    
    Åtgärden justerar kostnaden på de ursprungliga försäljningsrader som har kostnadsberäknats till -35,00 (5 enheter \*7,00) till -30.00 (5 enheter \*6,00). Detta beror på att lagermodellgruppen använder Först in, först ut (FIFO) och 6,00 per enhet är FIFO-kostnaden från den inköpsordern. Dessutom justerar åtgärden kostnaden på returförsäljningsraden för att matcha kostnaden per styck på den ursprungliga försäljningsraden. Därför justeras kostnaderna för returraden från 35,00 till 30,00.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]