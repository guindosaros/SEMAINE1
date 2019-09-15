### SEMAINE_1 : exercice de maison sur le resumer de la semaine 1
## Nom et Prenoms : Guindo Mahamadou
# THEME : QUIZ

### Models :
   * Users
   * Theme
   * Quiz
   * Question
   * Reponse
   * Note
   
### Creation des champs des Models :
```python

 class Users:
      "" Class Users de Django ""
   
 class Theme(models.Model):
   titre =  models.CharField(max_length=100)
   description = models.TextField()
   status = models.BooleanField(default=True)
   date_add =  models.DateTimeField(auto_now_add=True)
   date_upd =  models.DateTimeField(auto_now=True)
   image_theme = models.ImageField(upload_to='theme', blank=True)
     
  class Quiz(models.Model):
    titre =  models.CharField( max_length = 100 )
    description = models.TextField()
    status = models.BooleanField(default=True)
    nbre_quest = models.IntegerField(max_length=2)
    note_validation = models.IntegerField(max_length=3)
    date_add = models.DateTimeField(auto_now_add=True)
    date_upd = models.DateTimeField(auto_now=True)
    temps = models.DurationField()
    theme_id = models.ForeignKey(Theme,on_delete=models.CASCADE, related_name='theme_quiz')
     
  class Question(models.Model):
    enoncet = models.TextField()
    date_add = models.DateTimeField(auto_now_add=True)
    date_upd = models.DateTimeField(auto_now=True)
    status = models.BooleanField(default=True)
    image_theme = models.ImageField(upload_to='question', blank=True)
    quiz_id  = models.ForeignKey(Quiz,on_delete=models.CASCADE, related_name='quiz_question')
        
 class Reponse(models.Model):
   reponse = models.TextField()
   point = models.IntegerField(max_length=2)
   date_add = models.DateTimeField(auto_now_add=True)
   date_upd = models.DateTimeField(auto_now=True)
   status = models.BooleanField(default=True)
   question_id = models.ForeignKey(Quiz,on_delete=models.CASCADE, related_name='question_reponse')
   
class Note(models.Model):
  note_totale = models.IntegerField(max_length=3)
  user_id = models.ForeignKey(User,on_delete=models.CASCADE, related_name='user_note')
  quiz_id = models.ForeignKey(User,on_delete=models.CASCADE, related_name='quiz_resultat')
  a_valider = models.BooleanField(default=False)
  date_add = models.DateTimeField(auto_now_add=True)
  date_upd = models.DateTimeField(auto_now=True)
      

```
### Explications de models Quiz  :
* un thème a plusieurs Quiz l'utilisateur peut sélectionner un thème et passer différent Quiz sur le thème
* A la création d'un quiz on donne le nombre qu'il faut pour valider le quiz et le temps de durée du quiz et Aussi le Nombre de Questions du quiz
* Chaque question crée est  attribué a un Quiz et Prend une réponse que l'on crée dans le models réponse chaque réponse a un point pour une reponse fausse ou une bonne reponse 
* Après Avoir passer un Quiz nous Avons une Note qui représente Notre resultat notetotal est la somme des point des réponse de chaque question d'un qui a_valider prend un Boolean si la note totale est superieur ou egale a la note de validation du quiz a valider devient true et le resulat  de la note est valider 








