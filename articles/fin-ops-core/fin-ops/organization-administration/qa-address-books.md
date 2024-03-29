---
title: Vanliga frågeställningar och svar om adressböcker
description: Den här artikeln finns svar på vanliga frågeställningar som rör adressböcker.
author: msftbrking
ms.date: 02/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DirPartyCheckDuplicate, DirPartyTable
audience: Application User
ms.reviewer: sericks
ms.custom: 23601
ms.assetid: b177fa0f-ac9a-415e-9498-15438e132f60
ms.search.region: Global
ms.author: brking
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0b7262bc0be5330ac239fbceff96108477e2a796
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8881034"
---
# <a name="address-books-faq"></a>Vanliga frågeställningar och svar om adressböcker

[!include [banner](../includes/banner.md)]

## <a name="how-do-i-check-for-duplicate-records"></a>Hur leta efter dubletter av poster?

Du kan söka efter dublettposter direkt på listsidan **Global adressbok** . Klicka på **Kontrollera dubbletter** i fönstret Åtgärd på fliken **Part** i gruppen **Underhåll**. Markera värdena som du vill inkludera i dubblettkontrollen.

## <a name="can-i-bulk-add-or-delete-party-records-from-an-address-book"></a>Kan jag lägga till i bulk eller ta bort partposter från en adressbok?

Ja, kan du lägga till flera partposter till en adressbok och även ta bort flera partposter.

- Om du vill lägga till flera partposter till en adressbok genom att välja parterna på listsidan **Global adressbok**. Klicka på **Tilldela parter** i fönstret Åtgärd på fliken **Part** i gruppen **Underhåll**. Välj adressböckerna som du vill lägga till de valda partposterna till och klicka sedan på **OK**. Alla markerade partposter läggs till i de valda adressböckerna.
- Ta bort flera partposter från en adressbok genom att välja parterna på listsidan **Global adressbok**. Klicka på **Ta bort parter** i fönstret Åtgärd på fliken **Part** i gruppen **Underhåll**. Välj adressböckerna från vilka du vill ta bort parterna och klicka sedan på **OK**. Alla markerade partposter tas bort från de valda adressböckerna.

## <a name="can-i-change-the-party-type-of-a-record-or-do-i-have-to-delete-the-old-record-and-create-a-new-one"></a>Kan ändra jag parttypen för en post eller jag måste ta bort den gamla posten och skapa en ny?

Då och då måste du kanske ändra parttypen för en post från person till organisation eller från organisation till person. Till exempel Nancy är medlem i säljteamet för Fabrikam i Storbritannien På en mässa i London träffar hon sex potentiella kunder. Nancy skapar en potentiell kundpartpost för varje potentiell kund. När Nancy sparar posterna skapas också varje post i den globala adressboken. Fabrikam har angett standardparttypen till organisation, men två av de potentiella kunderna ska ha posttypen person. När Nancy återvänder från mässan måste hon därför ändra parttypen för två av de potentiella kundposterna. Om du vill ändra en partpost till en annan parttyp måste du först skapa en ny partpost av den rätta typen in den globala adressboken. Du kopplar sedan den gamla partposten till den nya posten. Ta bort den ursprungliga partposten som har felaktig posttyp när du har gjort den nya partassociationen.

## <a name="how-do-i-change-the-name-or-address-of-a-party-record"></a>Hur ändrar namn eller adress för en partpost?

Du kan uppdatera namnet på en partpost och adresserna som är kopplade till posten när som helst.

- Öppna partposten och sedan klickar du på **Redigera** i åtgärdsfönstret för att uppdatera namnet på en partpost. Ange det nya namnet på parten och spara posten på snabbfliken **Allmänt**.
- Välj adressen till en partpost som du vill uppdatera genom att välja adressen på snabbfliken **Adresser**. Klicka på **Redigera** och ändra sedan adressen eller adressparametrarna på sidan **Redigera adress**.

## <a name="can-i-merge-two-or-more-party-records-into-one-record"></a>Kan jag sammanfoga två eller flera partposter till en post?

Ibland vill du kanske sammanfoga två eller flera partposter till en enskild post. Detta kan inträffa om du skapar en eller flera dubbelpartposter, antingen på avsiktligt eller oavsiktligt. När du sammanfogar partposter väljer du en post att behålla. Informationen från övriga poster sammanfogas sedan till den här posten. Du upptäcker till exempel att information om Fabrikam lagras i tre partposter: A, B och C. Du vill behålla partpost A. Detta innebär att informationen som lagras i partposterna B och C sammanfogas till partposten A. Det finns fall där inte du kan sammanfoga partposter:

- Du kan inte sammanfoga partposter som är associerade med samma partroll, till exempel kund eller leverantör i samma juridiska person. Exempelvis part A som är kopplad till en kund i den juridiska personen 123, och part B som är kopplad till en annan kund i den juridiska personen 123. Dessa partposter kan inte sammanfogas eftersom om de sammanfogas skulle den sammanfogade partposten associeras med flera kunder i samma juridiska person, och det är inte tillåtet. Dock kan posterna sammanfogas om part B är kopplad till en leverantör hos juridisk person 123 eller med en kund i en annan juridisk person.
- Du kan inte sammanfoga interna partorganisationsposter hos samma juridiska personen, team eller driftenhet.

## <a name="should-i-create-a-party-record-in-the-global-address-book-or-in-another-place-such-as-the-customer-or-vendor-page"></a>Ska jag skapa en partpost i den globala adressboken eller på en annan plats, som till exempel sidan Kund eller Leverantör?

Du kan ange partposter antingen i den globala adressboken eller på lämplig enhetssida. När du lägger till en post på en plats läggs samma post alltid till på den andra platsen. Om du till exempel lägger till en partpost för en kund i den globala adressboken, läggs posten även till på sidan **Kund**. Om du till exempel lägger till en partpost för en kund på sidan **Kund** läggs posten även till i den globala adressboken. Använd följande riktlinjer för att avgöra var du ska ange nya partposter:

- **Skapa en partpost när du är osäker på enhetstypen** – Om du måste skapa en partpost men inte känner till enhetstypen (du vet till exempel inte om enheten är en kund eller en affärsmöjlighet), skapa posten i den globala adressboken. Du kan välja enhetstypen senare.
- **Skapa en partpost när du känner till enhetstypen** – Om du känner till enhetstypen för parten kan du skapa en post på den lämpliga sidan för den typen. Skapa till exempel en post för en kund på sidan **Kund**. När du skapar och sparar en post genom att använda lämplig enhetssida skapas posten automatiskt i den globala adressboken.

## <a name="can-i-translate-address-information-for-party-records"></a>Kan jag översätta adressinformation för partposter?

Du kan ställa in översättningar av adressinformation så att informationen visas i ditt användarspråk (systemspråk) i ditt program men på ett annat språk för dokument såsom försäljningsorder. Du kan ange översättningar för land/regionnamn, i adressyften och namnsekvenser. Ditt systemspråk är till exempel danska och du skapar en försäljningsorder för en kund i Frankrike. I detta fall kan du visa kundposten på danska i programmet, men visa adressinformation på franska på den utskrivna försäljningsordern. När du ställer in översättningar måste du ange en översättning för varje artikel på listan. Alla artiklar som du inte anger någon översättning för visas på systemspråket. Ditt systemspråk är till exempel danska och du skickar ett dokument till en kund i Spanien. Om du inte har angett spanska (ESP) översättningar för adressinformationen, visas den informationen på danska både i programmet och på det utskrivna dokumentet.

## <a name="after-i-import-addresses-why-cant-i-edit-the-records"></a>Varför kan jag inte redigera posterna efter att jag importerat adresser?

När du importerar adresser finns det ett fält som kallas **IsLocationOwner**. Det här fältet anger om parten som är kopplad till platsen (adressen) är ägare till adressen. Om parten är ägare till adressen kan adressen redigeras när den parten används i den globala adressboken eller från huvudpostformuläret (till exempel kunden, leverantören eller arbetaren). Om parten inte är ägare till adressen går det inte att redigera posten. 

När du importerar adresser ska fältet **IsLocationOwner** vara inställt på **Ja** om du vill att adressen ska kunna redigeras av den associerade parten. Om fältet importeras på fel sätt kan platsägaren uppdateras i den globala adressboken.

Mer information om hur du ändrar platsägaren för en importerad adress finns i [Hantera platsägare](./global-address-book-location-owner.md).

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
