---
title: "Hantera leverantörssamarbetesanvändare"
description: "I det här avsnittet beskrivs hur du kan begära reservation av nya leverantörssamarbetesanvändare, samt hur du lägger till nya leverantörssamarbeteskontakter."
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: smmContactPerson, VendVendorContactPerson, VendVendorPortalUser
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 220744
ms.assetid: edc19ad0-3565-4d47-98ac-dda6098f63ac
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 80374d6dce8aa5d5f2e5afc0656b42236ac974ec
ms.openlocfilehash: 036e8079bd976087514a074529dd4593c5a2b0a5
ms.contentlocale: sv-se
ms.lasthandoff: 03/13/2018

---

# <a name="manage-vendor-collaboration-users"></a>Hantera leverantörssamarbetesanvändare

[!include[banner](../includes/banner.md)]


I det här avsnittet beskrivs hur du kan begära reservation av nya leverantörssamarbetesanvändare, samt hur du lägger till nya leverantörssamarbeteskontakter. 

Leverantörssamarbetsgränssnittet i Microsoft Dynamics 365 for Finance and Operations visar information om inköpsorder, fakturor och försändelselager till externa leverantörer. Du kan skapa nya lleverantörssamarbeteskontakter och begära att nya användare reserveras om du arbetar som en extern leverantör med säkerhetsrollen **Leverantörs-admin (extern)** eller liknande behörigheter. Du kan också utföra dessa uppgifter om du arbetar professionellt inom anskaffning. I det här avsnittet avser denna roll en yrkesperson inom anskaffning som arbetar inom det företag som äger Finance and Operations-instansen. Mer information om hur du använder leverantörssamarbete om du använder en extern leverantör finns i [Leverantör med kunder](vendor-collaboration-work-customers-dynamics-365-operations.md).  

Mer information om hur du använder leverantörssamarbete om du är inköpsspecialist, se [Leverantörssamarbete med externa leverantörer](vendor-collaboration-work-external-vendors.md).

## <a name="add-new-vendor-collaboration-contacts"></a>Lägg till nya lleverantörssamarbeteskontakter
Om du vill ge någon åtkomst till leverantörssamarbete, måste de först läggas till som en leverantörssamarbeteskontakt. Du kanske också vill lägga till kontakter för medarbetare inom företaget som inte använder leverantörssamarbete. De kan exempelvis utgöra kontaktpunkt för andra typer av anskaffningsinformation. Nya kontakter läggs till på sidan **Alla kontakter**, som du når via menyn **Leverantörssamarbete** &gt; **Kontakter**. För att lägga till en ny kontakt:

1.  Klicka på **Nytt.**
2.  Ange uppgifter för kontaktpersonen.
3.  Välj den juridiska person som de representerar på ditt företag, samt vilken juridisk person som de ska arbeta med på det företag som de ska samarbeta med. Du gör detta genom att välja ett par för **Juridisk person inom mitt företag**/**Juridisk person i kundföretaget**.
4.  Klicka på **Skapa**

Om du vill ta bort en kontakt kan du bara ta bort dem som du har skapat.

## <a name="vendor-collaboration-user-requests"></a>Användarbegäranden från leverantörssamarbete
Användarförfrågningar för leverantörssamarbeten kan göras av en yrkesperson inom anskaffning eller av en extern leverantörsadministratör.

-   Om du är en extern leverantör skickar du in begäran från sidan **Alla kontakter** i modulen **Leverantörssamarbete**.
-   Om du är verksam inom anskaffning skickar du in förfrågningar från sidan **Visa kontakter**. För att göra detta: I leverantörsposten, i avsnittet **Inställningar** i åtgärdsfönstret, väljer du **Kontakter** &gt; **Visa kontakter**.

Du kan ställa en begäran om reservera en användare, inaktivera en användare eller ändra säkerhetsroller. Om du är en extern leverantörsadministratör måste du registreras som en kontaktperson för de leverantörskonton som du vill göra användarbegäran för, och du måste ha åtkomst till leverantörssamarbetesgränssnittet för dessa leverantörskonton.  

När en begäran skickas in läggs den till i listan **Användarbegäran från leverantörssamarbete** i modulen **Leverantörssamarbete**, samt i listan **Användarbegäran från leverantörssamarbete** i modulen **Anskaffning och källa** (anskaffnings- och inköpsmodulen är inte tillgänglig för externa användare).

### <a name="provision-a-user"></a>Reservera en användare

Innan du kan begära att en ny användare reserveras, måste den personen ställas in som en kontakt för en eller flera leverantörskonton. För att skapa en begäran för en ny leverantörssamarbetesanvändare:

1.  På sidan **Alla kontakter** klickar du på **Reservera leverantörsanvändare**.
2.  Ange en e-postadress för användare. Denna adress används av användaren för att logga in på Finance and Operations. Om e-postadressen tillhör en domän som registrerats som en innehavare i Microsoft Azure, så måste e-postadressen vara ett befintligt Azure Active Directory (AAD)-konto för att reservationsprocessen ska slutföras. Om e-postadressen inte tillhör någon domän som har registrerats för Microsoft Azure, kommer ett ADD-konto att skapas som ett led i reserveringsprocessen, och den nya användaren kommer att få en inbjudan via mail. E-postadresser för konsumenter med domäner som exempelvis @hotmail.com, @gmail.com och @comcast.net kan inte användas för att registrera en Finance and Operations-användare.
3.  Ange alternativet **Åtkomst till leverantörssamarbete tillåten** som **Ja** för alla juridiska personer som användaren behöver åtkomst till.
4.  I avsnittet **Tilldela användarroller** väljer du kryssrutan **Tilldela** för de säkerhetsroller som den nya användaren ska få.
5.  Klicka på **Skicka**.

När begäran om leverantörsanvändare skickas in, anges fältet **Åtkomst för leverantörssamarbete medges** som **Ja** för valt leverantörskonto, och ett nytt arbetsflöde för användarbegäran startas. Som en del av arbetsflödet skapas en ny användare i Finance and Operations, och säkerhetsroller tilldelas. Dessutom aktiveras en Azure B2B-tjänst som initierar en interaktion med Azure-portalen samt associerar ett nytt eller befintligt AAD-konto med Finance and Operations-användarkontot. Mer information finns i [vad är Azure AD B2B-samarbete?](https://docs.microsoft.com/en-us/azure/active-directory/active-directory-b2b-what-is-azure-ad-b2b).

### <a name="inactivate-a-user"></a>Inaktivera en användare

Det finns två sätt att ta bort åtkomsten till leverantörssamarbete för en användare:

-   På sidan **Kontakter** för leverantören anger du alternativet **Åtkomst till leverantörssamarbete tillåten** som **Nej** för kontakten. Detta kan göras individuellt per juridisk person som personen är en kontakt för. Detta alternativ kan bara användas av personer verksamma inom anskaffning.
-   Inaktivera hela användarkontot genom att skicka in en begäran om **Inaktivera leverantörsanvändare**.

För att begära att en användare avaktiveras:

1.  På sidan **Alla kontakter** klickar u på **Avaktivera** **leverantörsanvändare**.
2.  Skriv en kommentar i fältet **Affärsjustering**.
3.  Klicka på **Skicka**.

### <a name="modify-security-roles"></a>Ändra säkerhetsroller

Sidan **Bibehåll roller för leverantörsanvändare** är densamma som sidan **Reservera leverantörsanvändare** förutom att listan över säkerhetsroller kan redigeras.  

Om du vill begära att säkerhetsrollerna ändras för en användare:

1.  På sidan **Alla kontakter** klickar du på **Bibehåll** **roller för leverantörsanvändare**.
2.  Skriv en kommentar i fältet **Affärsjustering**.
3.  I avsnittet **Underhåll användarroller** väljer du de säkerhetsroller som du vill tilldela eller tar bort de som du vill bli av med.
4.  Klicka på **Skicka**.





