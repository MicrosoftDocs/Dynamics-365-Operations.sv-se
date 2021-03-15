---
title: Integrera leverantörer
description: Det här avsnittet beskriver processen för att integrera nya leverantörer. Det förklarar de åtgärder som krävs av olika roller under denna process.
author: RichardLuan
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendProspectiveVendorRegistrationRequests, SysUserRequestListPage, VendRequestListPage, VendRequestCompanyProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 081c2e5145a9175ace946e332e299247e706b548
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/16/2021
ms.locfileid: "5019889"
---
# <a name="onboard-vendors"></a>Integrera leverantörer

[!include [banner](../includes/banner.md)]

---

Nya leverantörer kan integreras och registreras som leverantörer i Microsoft Dynamics 365 Supply Chain Management baserat på information som samlas in från någon som representerar leverantören.

Processen består av följande steg, där olika roller utför åtgärder i systemet:

1. **Datahantering OData** – Importera enhet – Den första begäran är den potentiella leverantörens registreringsbegäran. Denna begäran kommer vanligtvis från en källa som exempelvis webbplats som kunden agerar värd för och som tillåter anonym åtkomst. Leverantörer kan registrera sig genom att tillhandahålla grundläggande information, till exempel leverantörens namn, berättigande, organisationsnummer samt kontaktpersonens namn och e-postadress. Begäran importeras via gränssnittet för datahantering.
2. **Listsida för registreringsbegäran för potentiell leverantör** - Baserat på den information som tillhandahålls i registreringsbegäran för potentiell leverantör beslutar en inköpsperson huruvida leverantören ska integreras. Inköpspersonen granskar den inkommande begäran på listsidan **Registreringsbegäran för potentiell leverantör**.
3. **Arbetsflöde för användarreserveringar** - När en inköpare har bekräftat informationen i en inkommande begäran och har beslutat att fortsätta med integreringsprocessen, reserverar arbetsflödet för användare den nya användaren och skickar en inbjudan via e-post att godkänna kontaktpersonen som en autentiserad användare av Microsoft Dynamics 365.
4. **Registreringsguide för leverantörer** - Leverantörens kontaktperson loggar in på med hjälp av det nya användarkontot. Han eller hon slutför registreringsguiden för leverantörer i syfte att tillhandahålla information som exempelvis adresser, företagsinformation, inköpskategorier och enkätfrågor.
5. **Arbetsflöde för godkännande** - En leverantörsförfrågan som innehåller registreringsinformationen skapas. Denna leverantörsförfrågan skickas till ett arbetsflöde och sedan vidare för granskning och godkännande.
6. **Skapande av en överordnad leverantör och ändring av användarroll** - När en leverantörsförfrågan har godkänts skapas en leverantörspost. Användarkontot för leverantörens kontaktperson får antingen behörighet för leverantörssamarbete, eller också inaktiveras det.

Följande tabell anger de steg och roller som ingår i processen.

| Roll och "process"       | Datahantering OData – enhetsimport | Listsida för registreringsbegäran för potentiell leverantör | Arbetsflöde för användarförfrågningar | Registreringsguide för leverantör | Godkännandearbetsflöde | Skapa en överordnad leverantör och ändring av användarroll |
|--------------------------|---|---|---|---|---|---|
| System                   | Begäran för en ny leverantör importeras. | | | | | När leverantörsförfrågan har godkänts skapas leverantörsposten. |
| Inköpare | | Starta integreringsprocessen. | | | Granska och acceptera eller avvisa leverantörsförfrågan. | |
| Administratör            | | | Skapa en användare i Supply Chain Management och Microsoft Azure. | | | |
| Leverantörens kontaktperson    | | | Skicka e-post till kontaktpersonen. | Registrera leverantörsinformation. | | |

Titta på det här korta videoklippet på YouTube för en snabb demonstration av leverantörens integreringsprocess [Hur du integrerar en ny leverantör i Finance and Operations](https://www.youtube.com/watch?v=0KUc3AGaTKk).

## <a name="importing-the-prospective-vendor-registration-request"></a>Importera begäran om registrering för potentiell leverantör

Registreringsbegäran för potentiell leverantör är en enhet i Supply Chain Management. Du kan ställa in systemet för att importera data via denna enhet. 

Följande tabell visar den information som denna enhet innehåller och som kan importeras.

| Fält                        | beskrivning |
|------------------------------|-------------|
| Leverantörsnamn                  | Namn på leverantören. |
| Affärsjustering       | Orsak(er) för leverantörsförfrågan. |
| Organisationsnummer          | Ett officiellt känt registreringsnummer. |
| Affärsområde             | Det affärsområde som leverantören är verksam inom. |
| Kontaktpersonens förnamn  | Förnamnet på den person som kommer att uppmanas att registrera information om leverantören. |
| Kontaktpersonens mellannamn | Mellannamnet på den person som kommer att uppmanas att registrera information om leverantören. |
| Kontaktpersonens efternamn   | Efternamnet på den person som kommer att uppmanas att registrera information om leverantören. |
| Kontaktpersonens e-postadress       | Den e-postadress som används för att skapa en ny användare i Supply Chain Management och som kommer att registreras i innehavarens Azure Active Directory (Azure AD)-konto. |
| Skickad den               | Det datum då begäran skapades i ett externt system. |
| Juridisk person                 | Den juridiska person där leverantören begär att bli en leverantör. Detta värde måste vara en kod för juridisk person som har registrerats i Supply Chain Management. Om inget värde erhålls genom importen används ett värde från parametrarna Anskaffning och inköp. |
| Leverantörstyp                  | Leverantören kan vara antingen en organisation eller en person. Leverantörstypen bestämmer hur leverantören slutligen skapas. |

När registreringsbegäran för potentiell leverantör importeras, visas den på listsidan **Registreringsbegäran för potentiell leverantör**. Via denna listsida kan en inköpare bjuda in användaren. En användarbegäran för att reservera användaren skickas till ett arbetsflöde.

## <a name="submitting-a-prospective-vendor-user-request"></a>Skicka in en användarbegäran för en potentiell leverantör

Syftet med en användarbegäran för potentiell leverantör är att reservera personen som skickade in den ursprungliga begäran, detta så att han eller hon kan logga in i Supply Chain Management genom att använda det e-postkonto som tillhandahålls i registreringsbegäran för potentiell leverantör.

Användarförfrågan för potentiell leverantör bearbetas av arbetsflödet för användarbegäran. Detta arbetsflöde kommunicerar via Azure AD B2B-samarbete. En användare med lämpliga säkerhetsinställningar skapas i Supply Chain Management.

Nya användare som har ställts in har följande säkerhetsroller:

- Extern systemanvändare
- Potentiell leverantör (extern)

Den nya användaren får ett e-postmeddelande som genereras av arbetsflödet för användarbegäran. Detta e-postmeddelande uppmanar användaren att logga in i systemet.

Mer information om hur du konfigurerar e-postmeddelandet och arbetsflödet i allmänhet finns i beskrivningen av ett arbetsflöde för användarbegäran i [Ställa in och underhålla leverantörssamarbete](set-up-maintain-vendor-collaboration.md).

## <a name="vendor-registration"></a>Leverantörsregistrering

En potentiell leverantörsanvändare som loggar in i Supply Chain Management får se den första sidan i registreringsguiden för leverantörer, där han eller hon kan ange information om leverantören.

Guiden visar konfigurationen för leverantörsförfrågan. Det land/den region där leverantören bedriver verksamhet avgör vilken information som efterfrågas i guiden och vilken information som är obligatorisk.

Mer information om hur du konfigurerar leverantörsförfrågan finns i [Skapa och underhålla leverantörssamarbete](set-up-maintain-vendor-collaboration.md). Följande tabell ger en översikt över sidorna i guiden och syftet med respektive sida.

| Sida                       | beskrivning |
|----------------------------|-------------|
| Land/region             | Landet eller regionen avgör vilken konfiguration för leverantörsbegäran som tillämpas på de återstående guidesidorna. Landet/regionen avgör också värden i sökningen **Skatteort**. |
| Villkor       | Denna sida kan vara tillgänglig beroende på konfigurationen för leverantörsbegäran. Om den är tillgänglig måste användaren godkänna villkoren för att fortsätta. |
| Leverantörsinformation         | Denna sida innehåller leverantörsnamnet, som anges automatiskt från den ursprungliga registreringsbegäran för potentiell leverantör. Den innehåller även organisationsnumret, leverantörens telefonnummer, faxnummer och e-postadress, samt leverantörens adresser för olika ändamål. |
| Kontaktpersonens uppgifter | Denna sida innehåller kontaktpersonens namn, som anges automatiskt från den ursprungliga registreringsbegäran för potentiell leverantör. Den innehåller även kontaktpersonens telefonnummer och e-postadress, samt kontaktpersonens adresser för olika ändamål. |
| Affärsinformation       | Denna sida innehåller momsregistreringsnummer (för olika länder eller regioner) samt antalet anställda. Där finns även information om huruvida verksamheten är minoritetsägd. |
| Anskaffningskategorier     | Denna sida innehåller anskaffningskategorier som leverantören begär godkännande för. Användaren kan välja kategorier i hierarkin över inköpskategorier. Du kan konfigurera antalet nivåer som ska visas i hierarkin i **Parametrar för anskaffning och inköp** &gt; **Leverantörssamarbete** under **Anskaffning och inköp** &gt; **Inställningar**. |
| Enkäter             | Guiden kan innehålla en uppsättning frågeformulär för leverantören. Frågeformulär som visas i guiden konfigureras antingen i leverantörsförfrågan eller per anskaffningskategori. Om frågeformulär konfigureras per anskaffningskategori, bestämmer de anskaffningskategorier som leverantören begär godkännande för de frågeformulär som visas i guiden. På sidan **Anskaffningskategorier** kan du lägga till ett frågeformulär under relevant kategori och ange aktivitetstypen som **Leverantörsintegrering**. |

När den potentiella leverantörsanvändaren slutför registreringsguiden för leverantören, skapas en leverantörsförfrågan.

## <a name="manually-or-automatically-submit-a-vendor-request"></a>Skicka in en leverantörsbegäran manuellt eller automatiskt

En leverantörsförfrågan kan skapas som ett utkast och skickas manuellt till ett arbetsflöde. Alternativt kan leverantörsförfrågan också skickas automatiskt till ett arbetsflöde när registreringsguiden för leverantörsregistrering har slutförts. En begäran kan skickas manuellt om exempelvis en inköpare vill bedöma huruvida begäran ska skickas genom en godkännandeprocess innan den skickas till arbetsflödet.

- Välj **Parametrar för anskaffning och inköp** &gt; **Leverantörssamarbete**, och välj sedan **Skicka registrering av potentiell leverantör till arbetsflödet automatiskt** för att konfigurera leverantörsförfrågan så att denna skickas automatiskt till ett arbetsflöde när registreringsguiden för leverantörer har slutförts.

## <a name="vendor-requests"></a>Leverantörsförfrågningar

Leverantörsförfrågan som är tillgängliga på sidan **Användarförfrågan för leverantörssamarbete**.

En leverantörsförfrågan innehåller den information som den potentiella leverantörsanvändaren angett i registreringsguiden för leverantörer.

Begäran låter dig granska information om leverantören och bestämma huruvida leverantören ska få bli en registrerad leverantör.

Leverantörsförfrågan ska skickas till ett arbetsflöde och dirigeras till relevanta granskare och godkännare. Mer grundläggande information om hur du ställer in arbetsflöden finns i [Arbetsflöden för anskaffning och inköp](procurement-sourcing-workflows.md).

Följande tabell visar den status som en leverantörsförfrågan kan ha.

| Status                     | beskrivning |
|----------------------------|-------------|
| Utkast                      | Leverantörsförfrågan har inte skickats in ännu. |
| Begäran skickad          | Leverantörsförfrågan har skickats in, och första steget i arbetsflödet behandlas. |
| Pågående granskning             | Om det finns flera granskare i en arbetsflödesuppgift kan en granskare acceptera uppgiften att granska leverantörsförfrågan och sedan slutföra granskningen. Om endast en granskare finns kan den deltagaren slutföra granskningen genom att välja **Slutförd** i arbetsflödesåtgärden. Han eller hon behöver inte först acceptera arbetsuppgiften. |
| Förfrågan väntar på godkännande   | Leverantörsförfrågan har skickats till deltagarna för godkännande, och det finns ett alternativ att begära kompletterande uppgifter. En begäran om ytterligare information gör att arbetsuppgiften dirigeras tillbaka till avsändaren. Leverantörsförfrågan kan också godkännas eller avvisas när den har denna status. |
| Begäran om ändring av ansökan | Ytterligare information har begärts av godkännaren, och leverantörsförfrågan har dirigerats till den person som skickade leverantörsförfrågan. Inskickaren kan lägga till erforderliga uppgifter och sedan skicka tillbaka leverantörsförfrågan. Om en leverantörsförfrågan skickas på nytt, ändras statusen tillbaka till **Begäran väntar på godkännande**. |
| Begäran godkänd           | Denna status blir ett sluttillstånd. |
| Begäran avvisad           | Denna status blir ett sluttillstånd. |

## <a name="approving-a-vendor-request"></a>Godkänna en leverantörsförfrågan

När en leverantörsförfrågan har godkänts skapas ett leverantörskonto, och statusen **Godkänd** visas i både den ursprungliga registreringsbegäran för potentiell leverantör och i leverantörsförfrågan.

Innan du godkänner en leverantörsförfrågan på sidan **Ny leverantör** i snabbfliken **Allmänt** väljer du **Leverantörsgrupp** för att välja en leverantörsgrupp.

Om den potentiella leverantörsanvändaren ska ha åtkomst till Supply Chain Management i egenskap av en leverantörssamarbetesanvändare som representerar leverantören, ange då åtkomstbehörigheten för leverantörssamarbete som **Ja**. För att inaktivera det användarkonto den potentiella användaren använde för att registrera sig, ange denna behörighet som **Nej**.

Om åtkomstbehörigheten för leverantörssamarbete är **Ja** kommer, när leverantörsförfrågan godkänns, en begäran att skickas in med syfte att ändra användarens roller så att användaren har de roller som har definierats för typen **Leverantör** under **Externa roller**. Om denna behörighet är inställd på **Nej** när leverantörsförfrågan godkänns, kommer en begäran att skickas in med syfte att inaktivera användaren. I detta fall måste arbetsflödet för att inaktivera en användarförfrågan konfigureras.

För att ett leverantörskonto ska skapas när leverantörsförfrågan godkänns måste nummerserien för att skapa leverantörer leverantörsförfrågan ställas in på **Automatisk**.

En översikt över åtkomstbehörigheterna för en leverantörsamarbetssanvändare finns i [Ställa in och underhålla leverantörssamarbete](set-up-maintain-vendor-collaboration.md).

## <a name="rejecting-a-vendor-request"></a>Avvisa en leverantörsförfrågan

En orsak till avvisningen måste väljas i leverantörsförfrågan om en leverantörsförfrågan avvisas.

När en leverantörsförfrågan avvisas skickas en begäran om att inaktivera användaren. I detta fall måste arbetsflödet för att inaktivera en användarförfrågan konfigureras. Mer information finns i [Ställa in och underhålla leverantörssamarbete](set-up-maintain-vendor-collaboration.md).

När en leverantörsförfrågan avvisas, visas statusen **Avvisad** i både den ursprungliga registreringsbegäran för potentiell leverantör och i leverantörsförfrågan.

## <a name="deleting-a-prospective-vendor-registration-request-in-various-statuses"></a>Ta bort en registreringsbegäran för potentiell leverantör i olika statusvärden

Olika status för en registreringsbegäran för en potentiell leverantör ger en översikt över statusen för begäran.

Genom att tillämpa åtgärden **Ta bort** på registreringsbegäran för en potentiell leverantör kan du rensa och ta bort den uppsättning poster som har skapats, samt även inaktivera användarkontot. Resultatet av åtgärden **Ta bort** varierar beroende på statusen för registreringsbegäran för potentiell leverantör enligt följande tabell.


|          Status          |                                                                                     Statusbeskrivning                                                                                      |                                                                                                                                                            Resultat av åtgärden Ta bort                                                                                                                                                             |
|--------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|           Ny            |                                                                         Inga åtgärder har vidtagits på begäran.                                                                          |                                                                                                                                              Registreringsbegäran för potentiell leverantör tas bort.                                                                                                                                               |
|      Begärd användare      | När du väljer <strong>Bjud in användare</strong> ändras statusen till <strong>Användarförfrågan</strong>, och en begäran om potentiell användare skapas och skickas till ett arbetsflöde för användare. |                                                                                                          Du kan inte radera en registreringsbegäran med denna status för en potentiell användare eftersom arbetsflödet inte har avslutats.                                                                                                          |
|       Inbjuden användare       |                                                               Arbetsflödet för användarbegäran godkänns, och användaren skapas.                                                               |                                                                                                                      En begäran om att inaktivera användaren skapas, och registreringsbegäran för potentiell leverantör tas bort.                                                                                                                      |
| Registrering pågår |                                                         Den nya användaren har loggat in och har startat registreringsguiden för leverantör.                                                          |                                                                                     En begäran om att inaktivera användaren skapas, och registreringsbegäran för potentiell leverantör och de data som angavs i registreringsguiden för leverantör tas bort.                                                                                      |
|  Leverantörsförfrågan har skapats  |                                                                     Registreringsguiden för leverantör har slutförts.                                                                      | En begäran om att inaktivera användaren skapas, och registreringsbegäran för potentiell leverantör, de data som angavs i registreringsguiden för leverantör samt leverantörsbegäran tas bort.<blockquote>[!NOTE]<br>Du kan inte använda åtgärden <strong>Ta bort</strong> när leverantörsförfrågan befinner sig i en granskningsprocess i arbetsflödet.</blockquote> |
|         Godkänt         |                                                                               Leverantörsförfrågan godkänns.                                                                               |                                                                                                   Begäran om registrering av potentiell leverantör, de data som angavs i registreringsguiden för leverantör samt leverantörsförfrågan tas bort.                                                                                                    |
|         Avvisat         |                                                                               Leverantörsförfrågan avvisas.                                                                               |                                                                                                   Begäran om registrering av potentiell leverantör, de data som angavs i registreringsguiden för leverantör samt leverantörsförfrågan tas bort.                                                                                                    |



[!INCLUDE[footer-include](../../includes/footer-banner.md)]