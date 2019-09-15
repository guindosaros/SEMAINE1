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
```django
   class Users:
      "" Class Users de Django ""
   
   class Theme(models.Model):
     titre =  models.CharField(max_length=100)
     description = models.TextField()
     status = models.BooleanField(default=True)
     date_add =  models.DateTimeField(auto_now_add=True)
     date_upd =  models.DateTimeField(auto_now=True)
     imageTheme = models.ImageField(upload_to='theme', blank=True
     
  class Quiz(models.Model):
  





```









