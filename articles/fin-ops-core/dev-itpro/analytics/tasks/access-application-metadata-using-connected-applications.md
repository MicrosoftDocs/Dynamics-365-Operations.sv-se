---
title: Få åtkomst till programmets metadata med hjälp av anslutna program
description: Stegen i den här artikeln beskriver hur en användare av Regulatory Configuration Service kan utforma en ny modellmappning för elektronisk rapportering genom att använda metadata.
author: NickSelin
ms.date: 06/29/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-06-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 330683da986a551a9694833655122768d30499b1
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8906780"
---
# <a name="access-application-metadata-by-using-connected-applications"></a>Få åtkomst till programmets metadata med hjälp av anslutna program

[!include [banner](../../includes/banner.md)]

I följande steg förklaras hur en användare av Regulatory configuration service (RCS) i rollen Systemadministratör eller Utvecklare av elektronisk rapportering kan utforma en ny modellmappning för elektronisk rapportering (ER) genom att använda metadata i Finance and Operations-programmet. Programdata kan nås online genom att använda det RCS-anslutna programmet. Exempel på ER-modellmappning kommer att konfigureras för åtkomst till utländska handelstransaktioner. För att slutföra dessa steg i RCS måste du först slutföra stegen i ämnet [Skapa en konfigurationsleverantörer och välj de som aktiva](er-configuration-provider-mark-it-active-2016-11.md) Om du inte har slutfört stegen i ämnet [Få åtkomst till programdata genom att använda ER-konfiguration](access-application-metadata-er-configuration.md), ladda ner [Exempelsidan för Elektronisk rapportering](https://download.microsoft.com/download/0/4/e/04e13839-e423-442b-a6c2-dd35b1045c2d/Dynamics%20365%20for%20Finance%20and%20Operations%208.1%20Electronic%20reporting%20task%20guides.zip) för att hämta och spara följande ER-konfigurationer: Utländsk handel metadata.xml; Utländsk handel model.xml; Utländsk handel mapping.xml och slutför sedan stegen i proceduren.

## <a name="prerequisites"></a>Förutsättningar
1. Gå till **Alla arbetsytor** > **Elektronisk rapportering**. 
2. Kontrollera att konfigurationsleverantören för exempelföretaget "Litware, Inc." är markerad som **aktiv** och är tillgänglig. Om du inte ser den här konfigurationsleverantören ska du först slutföra stegen i proceduren [Skapa konfigurationsleverantörer och välj dem som aktiva](er-configuration-provider-mark-it-active-2016-11.md). 

## <a name="get-required-er-configurations"></a>Skapa nödvändiga ER-konfigurationer
1. Klicka på **Rapporteringskonfiguration**. 
2. Om du redan har slutfört stegen i proceduren [Få åtkomst till programdata genom att använda ER-konfiguration](access-application-metadata-er-configuration.md) har du redan alla ER-konfigurationer (metadata för utländsk handel, modell- och mappningskonfiguration) i den aktuella RCS-instansresursen. Du kan hoppa över resten av stegen i den här underaktivitet. 
3. Klicka på **Byt**. 
4. Klicka på **Läs in från XML-fil**. 
5. Klicka på **Bläddra** och välj filen **Utländsk handel metadata.xml**. 
6. Klicka på **OK**. 
7. Klicka på **Byt**. 
8. Klicka på **Läs in från XML-fil**. 
9. Klicka på **Bläddra** och välj filen **Utländsk handel model.xml**. 
10. Klicka på **OK**. 
11. Klicka på **Byt**. 
12. Klicka på **Läs in från XML-fil**. 
13. Klicka på **Bläddra** och välj filen **Utländsk handel mapping.xml**. 
14. Klicka på **OK**. 

## <a name="register-a-connected-application"></a>Registrera kopplat program
1. Stäng sidan. 
2. Stäng sidan. 
3. Gå till **Alla arbetsytor** > **Elektronisk rapportering**. 
4. Klicka på **anslutna program**. 
5. Kontrollera att det konfigurerade programmet är Azure-baserat och tillgängligt för den aktuella RCS-användaren. Det krävs också att den aktuella RCS-användaren har åtkomst till det valda programmet och har registrerats som en användare av det här programmet som spelar en roll som ger dem behörighet att komma åt programmets metadata. 
6. Klicka på **Ny**. 
7. I fältet **Namn** ange MyConnectedApp. 
8. I fältet **program**, skriv https:// mycompany.operations.dynamics.com'. 
9. I fältet **klientinnehavare** skriver du "mycompany.onmicrosoft.com". 
10. Klicka på **Spara**. 
11. När du kontrollerar anslutningen till ett konfigurerat program klickar du på sidan **Anslut till fjärrprogram**, klicka på länken **Klicka här för att ansluta till valt fjärrprogram**. 
12. Klicka **kontrollera anslutning**. 
13. Klicka på **Stäng**. 
14. När anslutningsvalideringen är klar uppdateras informationen om version och klientorganisation för det konfigurerade programmet i det aktuella rutnätet. 

## <a name="review-existing-model-mapping-configuration"></a>Granska befintlig konfiguration för mappning
1. Stäng sidan. 
2. Klicka på **Rapporteringskonfiguration**. 
3. I trädet, expandera **Utländsk handelsmodell**. 
4. I trädet väljer du **Utländsk handelsmodell\Utländsk handelsmappning**. 
5. Expandera avsnittet **Förutsättningar**. 

    > [!NOTE]
    > Denna mappning refererar till konfigurationen för metadata. Programdata från denna konfiguration kommer att erbjudas när modellmappningen kommer att vara konstruerad. 

6. Klicka på **Designer**. 
7. Klicka på **Designer**. 
8. Välj **Dynamics 365 for Operations\Tabellregister** i trädet. 
9. Klicka på **Lägg till rot**. 
10. Ange eller välj ett värde i fältet **Register**. 

    > [!NOTE]
    > Denna mappning refererar till konfigurationen för metadata. Programdata från denna konfiguration kommer att erbjudas när modellmappningen kommer att vara konstruerad. 

11. Klicka på **Avbryt**. 
12. Stäng sidan. 
13. Stäng sidan. 

## <a name="assign-connected-application-to-model-mapping"></a>Tilldela kopplat program till modellmappning 
1. Klicka på **Redigera**. 
2. Välj **MyConnectedApp**-program. 

    > [!NOTE]
    > För närvarande refererar denna mappning till metadata för det markerade anslutna programmet. När samma mappning refererar till metadatakonfigurationen och det anslutna programmet samtidigt, används metadata för det anslutna programmet. 

3. Klicka på **Designer**. 
4. Klicka på **Designer**. 
5. Välj **Dynamics 365 for Operations\Tabellregister** i trädet. 
6. Klicka på **Lägg till rot**. 
7. Ange eller välj ett värde i fältet **Register**. 

    > [!NOTE]
    > Fler än två programtabeller erbjöds nu eftersom mappningen använder alla metadata för det anslutna program som har tilldelats för det. 

8. Klicka på **Avbryt**. 
9. Klicka på **Validera.** 

    > [!NOTE]
    > Vi har bundit element i datamodellen med objekt av datakällor som beskrivs genom att använda information om metadata för det anslutna program som har tilldelats den här mappningen. 

10. Stäng sidan. 
11. Stäng sidan. 

När du behöver utvärdera den här modellmappningen med hjälp av metadata i ett annat versionsprogram, registrerar du ett annat anslutet program, tilldelar det till den här modellmappningen och validerar det mot nya metadata.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
