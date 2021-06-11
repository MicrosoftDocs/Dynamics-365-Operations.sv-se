---
title: Redigera personliga uppgifter
description: I den här artikeln beskrivs hur du redigerar personuppgifter i självservice för medarbetare och chef.
author: andreabichsel
ms.date: 03/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HRMParameters, EssWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 51941
ms.assetid: 2cfb061a-a616-4bf9-9d98-9cde00039eec
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-03-19
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2170d3b8c476fb82786721512013eae45bb78ce5
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/18/2021
ms.locfileid: "6052155"
---
# <a name="edit-personal-information"></a>Redigera personliga uppgifter

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Du kan redigera dina personuppgifter i Dynamics 365 Human Resources i **arbetsytan Självbetjäning för medarbetare**.

De personuppgifter du kan redigera innehåller:

- Adresser
- Kontaktinformation
- Personliga kontakter
- Identifieringsnummer
- Betalningsmetod
- Bild som används i personal

>[!NOTE]
>Du kanske inte kan redigera vissa typer av personlig information, till exempel affärskontaktinformation. Mer information finns i [Begränsa redigering av personlig information](hr-employee-self-service-restrict-editing.md).

Parametrar som ställs in i den globala adressboken avgör vilka roller som kan se dina personuppgifter.

1. I personal, väljer du **Självbetjäning för medarbetare**.

2. Välj **redigera personuppgifter**.

3. Om du vill ändra din adress väljer du fliken **adresser**. Ändringar du gör visas i arbetsytan **personalhantering** för att avisera HR.

    - För att lägga till en ny adress, välj **Lägg till**.
    - Om du vill redigera en befintlig adress markerar du adressen och väljer sedan **redigera**.
    - Om du vill visa en karta väljer du **karta**.
    - Om du vill lägga till eller ta bort en kontakt väljer du **fler alternativ** och väljer sedan **Avancerat**. Under **Kontaktinformation**, välj **Lägg till** eller **Ta bort** och redigera fälten vid behov.
    - Om du vill ange tidszon, välj **fler alternativ** och väljer sedan **Avancerat**. Under **allmänt** redigerar du fälten om det behövs.

4. Om du vill ändra din kontaktinformation väljer du fliken **kontaktinformation**. Du kan tillhandahålla olika typer av kontaktinformation, t.ex. telefon, e-post och länkar till sociala medier. Du kan ange en kontaktinformation som primär, men du kan bara ställa in en av varje typ som primär.

    - För att lägga till en ny kontaktinformation, välj **Lägg till**. Redigera fälten efter behov.
    - Om du vill redigera en befintlig kontaktinformation väljer du artikeln och väljer sedan **redigera**. Redigera fälten efter behov.
    - Om du vill ange en kontaktinformation som privat markerar du artikeln, väljer **Avancerat** och ställer sedan in växlingsknappen på **privat** till **ja**. Välj **OK**.
      >[!NOTE]
      >Knappen **Avancerad** är inte tillgänglig om din administratör har aktiverat funktion **(förhandsversion) begränsa anställda från att lägga till eller redigera adress- och kontaktinformation för utvalda syften** i din miljö. Mer information finns i [Begränsa redigering av personlig information](hr-employee-self-service-restrict-editing.md).
  
5. Om du vill ändra dina personliga kontakter väljer du fliken **personliga kontakter**. Du kan ange nödkontakter, mottagare och beroenden. En kontakt kan vara en person eller en organisation. Funktionen **Hantering av förmåner** använder personlig kontaktinformation. För mer information, se [Konfigurera berättigandealternativ för personlig kontakt](hr-benefits-setup-contact-eligibility-options.md).

6. Om du vill ändra dina ID-nummer, t.ex. personnummer, väljer du fliken **ID-nummer**. Ändringar kan gå igenom en godkännandeprocess om organisationen har ställt in ett arbetsflöde för godkännande.

    - Välj **Ny** om du vill lägga till ett ID-nummer. Fyll i fälten efter behov och välj **spara**.
    - Om du vill redigera ett tal väljer du **redigera**. Redigera fälten efter behov och välj **spara**.

7. Om du vill ändra de metoder som du betalar efter väljer du fliken **Min betalningsinformation**. Den här fliken är endast tillgänglig om betalsätt har aktiverats i formuläret **personalparametrar**. HR kan aktivera **Bankutdrag**, **Kassa**, **Check**, **Elektronisk betalning** eller **Andra**. HR kan också inaktivera validering av elektroniska betalningar (används för amerikanska löner) samt validering av bankkonto och flödesnummer.

8. Om du vill ändra bilden som visas i personal för din profil väljer du fliken **bild**. Beroende på organisationens inställningar kan det hända att bilder cirkuleras för godkännande.

    - Om du vill överföra en bild väljer du **Överför ny bild**.
    - Om du vill ta bort en bild markerar du bilden och väljer **ta bort**.



[!INCLUDE[footer-include](../includes/footer-banner.md)]