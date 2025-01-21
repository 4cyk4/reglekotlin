//Query qui a partir d'une liste de sender typé "spam" ressort la liste de sender ayant envoyé des mails avec le memes sujet
// Liste des senders d'origine
let liste_senders = dynamic([""]);
// Q1 Liste des sujets a partir des senders
let sujets = EmailEvents
    where SenderFromAddress in (liste_senders)
    project Subject
    distinct Subject;
// Q2 jonction de la table des sujets extraits avec tous les mails pour extraire les senders
EmailEvents
    join kind=inner (
    sujets
) on Subject
    summarize by SenderFromAddress, Subject
//  summarize by SenderFromAddress
