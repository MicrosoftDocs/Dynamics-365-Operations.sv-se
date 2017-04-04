---
title: "Hantera leverantörssamarbetesanvändare"
description: "I det här avsnittet beskrivs hur du kan begära reservation av nya leverantörssamarbetesanvändare, samt hur du lägger till nya leverantörssamarbeteskontakter."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: smmContactPerson, VendVendorContactPerson, VendVendorPortalUser
audience: Application User, IT Pro
ms.search.scope: Operations, Core
ms.custom: 220744
ms.assetid: edc19ad0-3565-4d47-98ac-dda6098f63ac
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: f77012e7b64b7f153103e9bbe91e8ded202b509a
ms.openlocfilehash: 380f1bcdf7109dc12fd898199033eac7710d863c
ms.lasthandoff: 03/31/2017


---

# <a name="manage-vendor-collaboration-users"></a>Hantera leverantörssamarbetesanvändare

I det här avsnittet beskrivs hur du kan begära reservation av nya leverantörssamarbetesanvändare, samt hur du lägger till nya leverantörssamarbeteskontakter. 

Lleverantörssamarbetesgränssnittet i Microsoft Dynamics 365 for Operations visar information om inköpsorder, fakturor och försändelselager till externa leverantörer. Du kan skapa nya lleverantörssamarbeteskontakter och begära att nya användare reserveras om du arbetar som en extern leverantör med säkerhetsrollen **Vendor admin (external)** eller liknande behörigheter. Du kan också utföra dessa uppgifter om du arbetar professionellt inom anskaffning. I det här avsnittet avser denna roll en yrkesperson inom anskaffning som arbetar inom det företag som äger Dynamics 365 for Operations-instansen. Mer information om hur du använder samarbete leverantör om du använder en extern leverantör finns [leverantör med kunder](vendor-collaboration-work-customers-dynamics-365-operations.md).  

Se mer information om hur du använder leverantören samarbete om du är en upphandling professionella [leverantör samarbete till med externa leverantörer](vendor-collaboration-work-external-vendors.md).

## <a name="add-new-vendor-collaboration-contacts"></a>Lägg till nya lleverantörssamarbeteskontakter
Om du vill ge någon åtkomst till leverantörssamarbete, måste de först läggas till som en leverantörssamarbeteskontakt. Du kanske också vill lägga till kontakter för medarbetare inom företaget som inte använder leverantörssamarbete. De kan exempelvis utgöra kontaktpunkt för andra typer av anskaffningsinformation. Läggs nya kontakter på den **alla kontakter** som kan nås från den **leverantör samarbete**&gt;**kontakter** meny. För att lägga till en ny kontakt:

1.  Klicka på **New.**
2.  Ange uppgifter för kontaktpersonen.
3.  Välj den juridiska person som de representerar på ditt företag, samt vilken juridisk person som de ska arbeta med på det företag som de ska samarbeta med. Det gör du genom att välja en **juridisk person i företaget**/**juridisk person i kundens företag** par.
4.  Klicka på **Create.**

Om du vill ta bort en kontakt kan du bara ta bort dem som du har skapat.

## <a name="vendor-collaboration-user-requests"></a>Användarbegäranden från leverantörssamarbete
Användarförfrågningar för leverantörssamarbeten kan göras av en yrkesperson inom anskaffning eller av en extern leverantörsadministratör.

-   Om du använder en extern leverantör kan du skicka begäranden från den **alla kontakter** sidan inom den **leverantör samarbete** modul.
-   Om du är verksam inom anskaffning skickar du in förfrågningar från sidan **View contacts**. Gör om leverantörsposten i den **inställningar** avsnitt i åtgärdsfönstret väljer **kontakter**&gt;**Visa kontakter**.

Du kan ställa en begäran om reservera en användare, inaktivera en användare eller ändra säkerhetsroller. Om du är en extern leverantörsadministratör måste du registreras som en kontaktperson för de leverantörskonton som du vill göra användarbegäran för, och du måste ha åtkomst till leverantörssamarbetesgränssnittet för dessa leverantörskonton.  

När en begäran skickas in läggs den till i listan **Vendor collaboration user requests** i modulen **Vendor collaboration**, samt i listan **Vendor collaboration user request** i modulen **Procurement and sourcing** (anskaffnings- och inköpsmodulen är inte tillgänglig för externa användare).

### <a name="provision-a-user"></a>Reservera en användare

Innan du kan begära att en ny användare reserveras, måste den personen ställas in som en kontakt för en eller flera leverantörskonton. För att skapa en begäran för en ny leverantörssamarbetesanvändare:

1.  I den **alla kontakter** klickar du på **bestämmelse leverantörsanvändare**.
2.  Ange en e-postadress för användare. Denna adress används av användaren för att logga in på Dynamics 365 for Operations. Om e-postadressen tillhör en domän som registrerats som en innehavare i Microsoft Azure, så måste e-postadressen vara ett befintligt Azure Active Directory (ADD)-konto för att reservationsprocessen ska slutföras. Om e-postadressen inte tillhör någon domän som har registrerats för Microsoft Azure, kommer ett ADD-konto att skapas som ett led i reserveringsprocessen, och den nya användaren kommer att få en inbjudan via mail. Klienten e adresser med domäner som @hotmail.com, @gmail.com, eller @comcast.netkan inte användas för att registrera en Dynamics 365 för åtgärder som användaren.
3.  Ange alternativet **Vendor collaboration access allowed** som **Yes** för alla juridiska personer som användaren behöver åtkomst till.
4.  I avsnittet **Assign user roles** väljer du kryssrutan **Assign** för de säkerhetsroller som den nya användaren ska få.
5.  Klicka på **Skicka**.

När leverantörsanvändarförfrågan skickas den **behörighet, leverantör samarbete** har tilldelats **Ja** för det valda leverantörskontot och en användare begär arbetsflödet startas. Som en del av arbetsflödet skapas en ny användare i Dynamics 365 for Operations, och säkerhetsroller tilldelas. Dessutom aktiveras en Azure B2B-tjänst som initierar en interaktion med Azure-portalen samt associerar ett nytt eller befintligt AAD-konto med Dynamics 365 for Operations-användarkontot.

### <a name="inactivate-a-user"></a>Inaktivera en användare

Det finns två sätt att ta bort åtkomsten till leverantörssamarbete för en användare:

-   På sidan **Contacts** för leverantören anger du alternativet **Vendor collaboration access allowed** som **No** för kontakten. Detta kan göras individuellt per juridisk person som personen är en kontakt för. Detta alternativ kan bara användas av personer verksamma inom anskaffning.
-   Inaktivera hela användarkontot genom att skicka in en begäran om **Inaktivera leverantörsanvändare**.

Så här begär du en användare inaktiveras:

1.  I den **alla kontakter** klickar du på **inaktivera****leverantörsanvändare**.
2.  Skriv en kommentar i fältet **Business justification**.
3.  Klicka på **Skicka**.

### <a name="modify-security-roles"></a>Ändra säkerhetsroller

Den **Hantera användarroller leverantören** sidan är densamma som den **bestämmelse leverantörsanvändare** sida förutom att du kan redigera listan över säkerhetsroller.  

Begära att säkerhetsroller ändras för en användare:

1.  I den **alla kontakter** klickar du på **upprätthålla****leverantör användarroller**.
2.  Skriv en kommentar i fältet **Business justification**.
3.  I avsnittet **Maintain user roles** väljer du de säkerhetsroller som du vill tilldela eller tar bort de som du vill bli av med.
4.  Click **Submit**.



