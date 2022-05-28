---
title: Skapa och underhåll leverantörssamarbete
description: Det här avsnittet förklarar hur du ställer in leverantörssamarbete i Dynamics 365 Supply Chain Management. Här förklaras också hur du inför nya leverantörers samarbetsanvändare och hanterar säkerhetsrollerna för dessa användare.
author: GalynaFedorova
ms.date: 12/03/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DirExternalRole, SysUserRequestListPage, VendVendorPortalUsers, WorkflowTableListPageRnr
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.custom: 220774
ms.assetid: 69d05e8b-7dc2-48ea-bc24-bea9ac963579
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 4b59513d86426d3c1bfd759b9aabc331e58d5423
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/03/2022
ms.locfileid: "8677574"
---
# <a name="set-up-and-maintain-vendor-collaboration"></a>Skapa och underhåll leverantörssamarbete

[!include [banner](../includes/banner.md)]

Lleverantörssamarbetesgränssnittet visar en begränsad uppsättning information om inköpsorder, fakturor och försändelselager till användare av externa leverantörer. Från det här gränssnittet kan en leverantör också svara på anbudsförfrågningar och visa och redigera grundläggande företagsinformation.

Det här avsnittet förklarar hur du ställer in leverantörssamarbete i Dynamics 365 Supply Chain Management. Här förklaras också hur du ställer in ett arbetsflöde för nya leverantörers samarbetsanvändare och hu du hanterar säkerhetsrollerna för dessa användare.

> [!NOTE]
> Informationen om inställningen av säkerhetsroller för leverantörssamarbete gäller bara för den aktuella versionen av Ekonomi och drift. I Microsoft Dynamics AX 7.0 (februari 2016) och Microsoft Dynamics AX programversion 7.0.1 (maj 2016) kan du samarbeta med leverantörer med hjälp av modulen **Leverantörsportal**. Mer information om användarbehörigheter för Leverantörsportalen i Microsoft Dynamics AX, se [användarsäkerheten för leverantörsportalen](configure-security-vendor-portal-users.md).

## <a name="set-up-vendor-collaboration-security-roles"></a>Skapa säkerhetsroller för leverantörssamarbete

Ett anskaffningsproffs eller en leverantör som har tillräcklig behörighet en leverantör som har tillräckligt med behörigheter kan begära att en kontaktperson tillhandahålls som en användare genom att aktivera **Reservera leverantörsanvändare** på kontaktpersonsposten. Under försörjningsprocessen väljs användarbehörigheter för den nya externa användaren, och den nya leverantörsanvändarförfrågan skickas. Det är viktigt att du anger användarbehörigheter som går att välja på rätt sätt i leverantörens användarbegäran. I annat fall kan leverantörer beviljas åtkomst till information som de inte ska ha tillgång till i Supply Chain Management.

### <a name="set-up-the-security-roles-that-are-available-for-selection-when-a-new-user-request-is-used-for-a-contact-person"></a>Ställ in de säkerhetsroller som är tillgängliga för urval när en ny användarbegäran används för en kontaktperson

1. Välj **System administration** &gt; **Säkerhet** &gt; **Externa roller**.
2. Välj **Ny** och välj sedan en säkerhetsroll och partirollen **Leverantör**.

Du kanske vill lägga till rollerna **Leverantörsadministratör (extern)** och **Leverantör (extern)** som finns i Supply Chain Management. Du kan även använda säkerhetsroller som ditt företag har skapat.

Du bör bara göra rollen **Leverantörsadministratör (extern)** tillgänglig om leverantörer ska kunna skapa nya kontakter, skicka användarförfrågningar från leverantörer för samarbete med nya användare och ändra användarinformation och hantera dessa förfrågningar via ett arbetsflöde.

Om du tänker ställa in leverantörskontakter och -användare manuellt kan du bara göra rollen **Leverantör (extern)** tillgänglig. Denna roll kommer sedan att vara den enda rollen som kan begäras via en leverantörsanvändarbegäran.

> [!NOTE]
> Rollen **SystemUser** beviljas automatiskt när du manuellt skapar ett nytt användarkonto. Därför måste du ta bort rollen och tilldela rollen **SystemExternalUser**.  Om nya användarkonton skapas via arbetsflödet som initieras av en leverantörsanvändares begäran att tilldela en ny användare, tilldelas en eller flera roller som du har ställt in för leverantörssamarbete och rollen **SystemExternalUser**. 

#### <a name="vendor-admin-external-security-role"></a>Säkerhetsrollen Leverantörsadministratör (extern)

Rollen **Leverantörsadministratör (extern)** kan användas för externa leverantörer som underhåller leverantörens kontaktinformation och gör förfrågningar om att tillhandahålla nya användare av leverantörssamarbete. Externa användare med den här säkerhetsrollen kan utföra följande uppgifter:

- Visa och ändra kontaktpersoninformation, t.ex. personens titel, e-postadress och telefonnummer.
- Lägg till en ny eller befintlig kontaktperson till leverantörskontona som de är kontaktperson för.
- Ta bort alla kontaktpersoner som de har skapat.
- Aktivera eller inaktivera associationen mellan en kontaktperson och ett leverantörskonto. Efter att kopplingen mellan en kontaktperson och ett leverantörskonto har inaktiverats kan kontaktpersonen inte hänvisas till på nya inköpsorder eller andra dokument.
- Neka eller tillåt en kontaktpersons åtkomst till dokument i gränssnittet för leverantörssamarbete som är specifika för leverantörskontot. När kopplingen mellan en kontaktperson och ett leverantörskonto har inaktiverats, nekas alltid åtkomst till dokument som är specifika för leverantörskontot.
- Begära ett nytt användarkonto för en kontaktperson med åtgärden **Provisionsanvändare**.
- Begär att kontaktpersonens användarkonto ska inaktiveras.
- Begära att en kontaktpersons användarkonto ändras för att lägga till eller ta bort säkerhetsroller.
- isa anbudsförfrågningar.

#### <a name="vendor-external-security-role"></a>Säkerhetsrollen leverantör (extern)

Rollen **Leverantör (extern)** kan användas för externa leverantörer som arbetar med inköpsorder. Externa användare med den här säkerhetsrollen kan utföra följande uppgifter:

- Besvara och visa information om inköpsorder.
- Underhåll leverantörssamarbetsfakturor.
- Visa försändelselager.
- Visa och svara på anbudsförfrågningar.
- Visa leverantörsinformation.

## <a name="set-up-security-roles-that-are-used-when-prospective-vendors-are-onboarded"></a>Ställ in säkerhetsroller som används när potentiella leverantörer blir inbyggda

Du måste ställa in en extern säkerhetsroll för leverantörer som initieras via en potentiell registreringsbegäran för leverantörer. Den här rollen tilldelas nya användare under försörjningsprocessen som kontrolleras av arbetsflödet för typen **Arbetsflöde för användarbegäran (plattform)**. Mer information finns i avsnittet [Ställ in arbetsflöden för att bearbeta användarförfrågningar från leverantörssamarbete](#set-up-workflows-to-process-vendor-collaboration-user-requests) längre fram i det här avsnittet.

Information om hur du introducerar potentiella leverantörer finns [introducera leverantörer](vendor-onboarding.md).

### <a name="set-up-a-security-role-that-is-used-when-a-new-prospective-vendor-user-request-is-submitted"></a>Ställ in en säkerhetsroll som används när en ny begäran om leverantörsanvändare skickas in

1. Välj **Systemadministration** > **Säkerhet** > **Externa roller**.
2. Välj **Ny** och välj sedan en säkerhetsroll och partirollen **Potentiell leverantör**.

Du bör lägga till rollen **Potentiell leverantör (extern)** som finns i Supply Chain Management.

Säkerhetsrollen beviljar endast åtkomst till den nya guiden för leverantörsregistrering.

## <a name="set-up-workflows-to-process-vendor-collaboration-user-requests"></a>Skapa arbetsflöden som bearbetar användarförfrågningar om leverantörssamarbete

För att garantera att alla relevanta uppgifter är slutförda och att godkännanden ges, måste du ställa in arbetsflöden för hantering av användarbegäranden om leverantörssamarbetsflöde.

Användarförfrågningar om leverantör samarbete skickas antingen av externa leverantörer med säkerhetsrollen **Leverantörsadministratör (extern)** eller liknande behörigheter, eller av anskaffningspersonal i ditt företag. De kan också genereras från potentiella leverantörsregistreringsförfrågningar under processen för leverantörsregistrering.

Det finns tre typer av begäranden:

- Begäran att skapa en ny användare
- Förfrågningar om att inaktivera en befintlig användare
- Begäran om ändring av säkerhetsrollerna för en befintlig användare

För mer information om användarförfrågningar från leverantörssamarbete, se [Hantera användare av leverantörssamarbete](manage-vendor-collaboration-users.md).

Du måste skapa två eller fler arbetsflöden för att kunna bearbeta alla tre typerna av användarbegäranden för leverantörssamarbetsflöde. Nya arbetsflöden skapas på sidan **Användararbetsflöden**.

### <a name="example-of-a-workflow-for-provisioning-new-users-and-modifying-security-roles"></a>Exempel på ett arbetsflöde där nya användare kan reservering och ändring av säkerhetsroller

Om du vill hantera leverantörsanvändarförfrågningar för att skapa nya användare och ändra säkerhetsroller, kan du skapa ett förgreningsvillkor i början av arbetsflödet. På det här sättet används en annan förgrening av arbetsflödet, beroende på om begäran är att skapa en ny användare eller ändra en befintlig användare.

För att ställa in denna förgrening, skapa ett nytt arbetsflöde för **Arbetsflödet för användarbegäran (plattform)**. Förgreningarna i arbetsflödet kan innehålla följande element.

#### <a name="branch-to-provision-new-users"></a>Förgrening för att skapa nya användare

1. Tilldela en godkännandeuppgift till den person som ansvarar för godkännandet av att nya användare ska beviljas åtkomst till leverantörens samarbetsinformation.
2. Tilldela en uppgift till den person som är ansvarig för begäran om nya Microsoft Azure Active Directory (Azure AD) användarkonton i Azure-portalen. Använd den fördefinierade uppgiften **Skicka Azure B2B användarinbjudan** för det här steget. B2B-användare kan automatiskt exporteras till Azure AD. Använd den fördefinierade **Etablera Azure AD B2B-användaren**. Mer information finns i [Exportera B2B-användare till Azure AD](../../fin-ops-core/dev-itpro/sysadmin/implement-b2b.md).
3. Tilldela en godkännandeuppgift till den person som överför till Azure. Om en kontonummer inte skapats, avvisar denna person uppgiften och avslutar arbetsflödet. Denna godkännandeuppgift kan hoppas över om du har inkluderat steget som automatiskt exporterar nya användarkonton till Azure via B2B-programgränssnittet (API).
4. Lägg till en automatisk uppgift som gör att en ny användare kan läggas till. Använd den fördefinierade uppgiften **Användare av automatiserad etablering** för det här steget.
5. Lägg till en uppgift som meddelar den nya användaren. Du kanske vill skicka ett välkomstmeddelande till den nya användaren, som innehåller en URL för Supply Chain Management. E-postmeddelandet kan använda en mall som du skapar på sidan **E-postmeddelanden** och sedan välja på sidan **Användararbetsflödesparametrar**.  Mallen kan innehålla taggen **%portalURL%**. När välkomstmeddelandet genereras ersätts det här märket av URL:en för Supply Chain Management-innehavare.

    > [!NOTE]
    > Det här arbetsflödet kan användas i flera olika scenarier där användarna måste registrera sig. Det kan till exempel användas när potentiella leverantörer eller kontaktpersoner kräver ett konto för leverantörssamarbete. Därför ska du formulera e-postmeddelandet som ett allmänt uttryck som kan användas för flera syften.

#### <a name="branch-to-modify-security-roles"></a>Förgrening för ändring av säkerhetsroller

1. Tilldela en godkännandeuppgift till den person som är ansvarig för godkännandet av ändringar av säkerhetsrollerna.
2. Lägg till en automatisk uppgift som lägger till eller tar bort relevanta säkerhetsroller. Använd den uppgiften **Användare av automatiserad etablering** för det här steget.

### <a name="example-of-a-workflow-for-inactivating-a-user"></a>Exempel på ett arbetsflöde där en användare inaktiveras

Skapa ett arbetsflöde med typen **Inaktivera arbetsflödesplattform för användarbegäran** och lägg sedan till följande uppgifter.

1. Tilldela en godkännandeuppgift till den person som är ansvarig för acceptera förfrågningar om att inaktivera användare. Du kan lägga till villkor för att automatisera det här godkännandesteget.
2. Lägg till en automatisk uppgift som inaktiverar användaren. Använd den uppgiften **Automatisk användarinaktivering** för det här steget.
3. Lägg till alla rensningsuppgifter som behövs. Du kan till exempel lägga till en uppgift som tar bort kontot från katalogen i Azure-portal.

## <a name="enable-vendor-collaboration-for-a-specific-vendor"></a>Aktivera leverantörssamarbete för en specifik leverantör

Innan du skapar ett användarkonto för någon som ska använda leverantörssamarbete måste du konfigurera leverantören så att den kan använda leverantörssamarbete. Gå till sidan **Leverantörer** och ange fältet **Samarbetesaktivering** på fliken **Allmänt**. Följande alternativ är tillgängliga:

- **Aktiv (IO bekräftas automatiskt)** - Inköpsorder bekräftas automatiskt när leverantören godkänner dem utan ändringar.
- **Aktiv (IO bekräftas inte automatiskt)** – Din organisation måste manuellt bekräfta inköpsorder det att leverantören har godkänt dem.

> [!NOTE]
> Anskaffningspersonal i ditt företag kan också genomföra den här uppgiften.

## <a name="troubleshoot-the-provisioning-of-new-vendor-collaboration-users"></a>Felsöka nya användare av leverantörssamarbete

Nya användare av leverantörssamarbete tillhandahålls via arbetsflödet som du ställer in för att bearbeta användarförfrågningar från leverantörssamarbete av typen **Etablera användare av leverantör**.

Om e-postadressen till en ny samarbetsanvändare för leverantörer tillhör en domän som har registrerats med Azure som innehavare (det vill säga om det är ett hanterat domänkonto), måste e-postadressen vara ett befintligt Azure AD konto. Annars kan etableringsprocessen inte slutföras.

Mer information om den process som används i uppgiften **Skicka Azure B2B användarinbjudan** i arbetsflödet för Azure AD kontohantering finns i [Azure Active Directory B2B-samarbete](/azure/active-directory/external-identities/what-is-b2b).

## <a name="additional-resources"></a>Ytterligare resurser

[Leverantörssamarbete med externa leverantörer](vendor-collaboration-work-external-vendors.md)

Se en kort video om leverantörens introduktionsprocess: [introducera en ny leverantör](https://www.youtube.com/watch?v=0KUc3AGaTKk&feature=youtu.be)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
