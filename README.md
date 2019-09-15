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
```bash
   class Users:
      "" Class Users de Django ""
   
   class Theme(models.Model):
     titre =  models.CharField(max_length=100)
     description = models.TextField()
     status = models.BooleanField()
     date_add =  models.DateTimeField(auto_now_add=True)
     date_upd =  models.DateTimeField(auto_now=True)
     image_theme = models.ImageField(upload_to='theme', blank=True
     
  class Quiz(models.Model):
     titre =  models.CharField(max_length=100)
     description = models.TextField()
     status = models.BooleanField(default=True)
     nbre_quest = models.IntegerField(max_length=2)
     note_validation = models.IntegerField(max_length=3)
     date_add = models.DateTimeField(auto_now_add=True)
     date_upd = models.DateTimeField(auto_now=True)
     theme_id = models.ForeignKey(Theme,on_delete=models.CASCADE, related_name="theme_du_quiz")
     
  class Question(models.Model):
        enoncet = models.TextField()
        date_add = models.DateTimeField(auto_now_add=True)
        date_upd = models.DateTimeField(auto_now=True)
        quiz_id  = models.ForeignKey(Quiz,on_delete=models.CASCADE, related_name="question_du_quiz")
     
        
     
     





```









