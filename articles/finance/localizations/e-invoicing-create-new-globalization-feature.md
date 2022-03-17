---
title: Skapa en globaliseringsfunktion
description: Detta ämne förklarar hur du skapar en globaliseringsfunktion.
author: dkalyuzh
ms.date: 02/14/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkalyuzh
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 197a5b983b307758425b1acc1f354d0a8bfbf8a1
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/02/2022
ms.locfileid: "8371821"
---
# <a name="create-a-globalization-feature"></a>Skapa en globaliseringsfunktion

[!include [banner](../includes/banner.md)]

Du kan skapa en funktion för e-fakturering från grunden, eller också basera den på en befintlig funktion. När du skapar en funktion från grunden måste du lägga till konfigurationer för elektronisk rapportering (ER) och andra komponenter manuellt, exempelvis information om funktionsinställningar och programinställningar. När du skapar en funktion som baseras på en befintlig funktion ärver den nya funktionen alla basfunktionens konfigurationer och parametrar. Du kan granska vad som kopierats från basfunktionen till den nya funktionen.

## <a name="create-a-feature-from-scratch"></a>Skapa en funktion från grunden

Detta avsnitt förklarar hur du skapar en funktion för e-fakturering när det inte finns någon färdig globaliseringsfunktion i den globala databasen för dina affärsscenarier.

Följ de här stegen om du vill skapa en funktion för e-fakturering.

1. Logga in på ditt konto för Regelkonfigurationstjänst (RCS).
2. I arbetsytan **globaliseringsfunktion** i avsnittet **Funktioner**, välj panelen **e-faktura**.
3. Välj **Lägg till** och välj sedan alternativet **Ny funktion** i den nedrullningsbara dialogrutan.
4. Ange ett namn och en beskrivning för funktionen för e-fakturering.
5. Välj **skapa funktion**. Den första versionen av den nya funktionen visas till höger på sidan och har statusen **Utkast**.

    Sedan måste du lägga till ER-konfigurationer och funktionsinställningar. Innan du lägger till nya eller befintliga ER-formatkonfigurationer måste du kontrollera att dessa finns i den lokala RCS-databasen.

6. Välj den funktion för e-fakturering som du arbetar med.
7. Välj **Konfigurationer** på fliken **Lägg till**.
8. I rutnätet **Konfigurationer** bläddrar du till och väljer de formatkonfigurationer som krävs för bearbetningsförloppet (t.ex. för att generera e-fakturafiler eller bearbeta svar från externa webbtjänster).
9. Välj **OK**. Du kan nu använda konfigurationerna för åtgärder i bearbetningsförloppet. För mer information, se [Arbeta med konfigurationer](e-invoicing-work-configurations.md).
10. Lägg till inställningar för en e-faktureringsfunktion genom att skapa den på fliken **Inställningar** på sidan **Ny funktion**. Mer information finns i [Arbeta med funktionsinställningar](e-invoicing-feature-setup.md).
11. Slutför konfigureringen och distribuera funktionen för e-fakturering till tjänstemiljön. För mer information, se [Slutföra, publicera och distribuera en globaliseringsfunktion](e-invoicing-complete-publish-deploy-globalization-feature).

### <a name="create-file-format-configurations-that-are-derived-from-the-existing-invoice-model"></a>Skapa filformatskonfigurationer som härleds från den befintliga fakturamodellen

Du kan hoppa över det här avsnittet om du inte behöver skapa ER-konfigurationer men kan återanvända befintliga versioner som bas.

Den här proceduren visar hur du skapar de filformatskonfigurationer som krävs för den nya funktionen för e-fakturering som du vill skapa. Skapa e-fakturafilformatskonfigurationen och alla andra filformatskonfigurationer som din nya funktion för e-fakturering kräver.

1. Logga in på RCS-kontot.
2. På arbetsytan **Elektronisk rapportering** väljer du panelen **Rapporteringskonfiguration**.
3. Välj **Fakturamodell** eller, för brasilianska scenarier, **Skattemodell**.
4. Välj **Skapa konfiguration** och sedan, i den nedrullningsbara dialogrutan, alternativet **Faktura formatbaserad på datamodell**.
5. Ange ett namn och en beskrivning för formatkonfiguration.
6. I fältet **Formattyp** ska du välja filtilläggstyp..
7. I fältet **Datamodelldefinition** väljer du den rotstruktur som du vill mappa ditt format till. **InvoiceCustomer** används till exempel för formaten för kundfaktura.
8. Välj **Skapa konfiguration**.
9. Välj den nya formatkonfigurationen.
10. Välj **Designer** och använd verktyget Formatdesigner när du vill konfigurera fillayouten så att den uppfyller specifikationerna för filformatet.
11. Stäng sidan.
12. På snabbfliken **Versioner**, välj **ändra status** \> **slutförd**.
13. Välj **Ändra status** \> **Dela** för att publicera formatkonfigurationen till Global databasen.

De nya konfigurationerna för filformat måste delas med Microsoft-domänen innan de kan förbrukas av e-faktureringstjänsten.

1. Välj den formatkonfiguration som du arbetar på. Konfigurationens status måste vara **Delad**.
2. Välj global **Versioner**, välj **Avancerad delning** \> **Global databas**.
3. I fliken **Delas med** väljer du **Organisation**.
4. I fältet **Parametrar** anger du **microsoft.com** för att dela formatkonfigurationen med Microsoft-domänen.
5. Välj **OK**.

## <a name="create-a-feature-that-is-based-on-an-existing-feature"></a>Skapa en funktion som baseras på en befintlig funktion

1. Logga in på RCS-kontot.
2. I arbetsytan **globaliseringsfunktion** i avsnittet **Funktioner**, välj panelen **e-faktura**.
3. I fältet **Konfigurationsleverantör** ser du till att din aktiva konfigurationsleverantör har valts. På så sätt visas den nya e-faktureringsfunktionen i listan när den har skapats. Om din aktiva konfigurationsleverantör inte väljs, filtreras den nya funktionen bort från listan.
4. Välj **Lägg till** och välj sedan alternativet **baserad på befintlig version i den nedrullningsbara dialogrutan**.
5. Ange ett namn och en beskrivning för funktionen.
6. I fältet **Basfunktion** väljer du funktionens basversion.
7. Välj **skapa funktion**. Funktionen skapas och bär statusen **Utkast**.
8. Granska funktionskomponenterna och ta reda på om det behövs några uppdateringar:

    - Granska konfigurationerna i den händelse att du skulle behöva anpassa ER-formaten och deras bindningar med formatmappningar för funktionsversionen.
    - Granska inställningarna om du skulle behöva anpassa fliken **Åtgärder**, fliken **Tillämplighetsregler** eller fliken **Variabler** för funktionsversionen.

9. Slutför konfigureringen och distribuera funktionen för e-fakturering till tjänstemiljön. För mer information, se [Slutföra, publicera och distribuera en globaliseringsfunktion](e-invoicing-complete-publish-deploy-globalization-feature).
