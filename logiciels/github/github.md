# Github

## Erreurs

### Push master to origin/master was rejected by remote

Cette erreur peut-être dûe au fait que votre adresse email a été mise en
statut privé dans vos paramètres Github alors même que vous tentez d'utiliser
cette adresse e-mail pour faire un push (qui affichera votre e-mail).

Solutions :

* Utilisez une nouvelle adresse dans vos paramètres Github.
* Repassez votre adresse github en mode public.

```text
https://github.com/settings/emails
```

![Passage de l'email en mode public](images/github_email_public.png "Passage de l'email en mode public")

Assurez-vous de décocher « Keep my email addesses private ».