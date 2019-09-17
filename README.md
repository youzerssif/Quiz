# Quiz
modèles Quiz Django

**Les modèles**

  ```
  
  class Quiz (models.Model):
      titre = models.CharField ( max_length = 255 )
      description = models.TextField ()
      date_add = models.DateTimeField ( auto_now_add = True )
      date_update = models.DateTimeField ( auto_now = True )
      statut = models.BooleanField ( default = True )
      user_id = models.ForeignKey('User', on_delete = models.CASCADE, related_name = 'user',)

  class Reponse (models.Model):
      description = models.TextField ()
      score = models.IntegerField(default = True )
      date_add = models.DateTimeField ( auto_now_add = True )
      date_update = models.DateTimeField ( auto_now = True )
      statut = models.BooleanField ( default = True )
      question_id = models.ForeignKey('Question', on_delete = models.CASCADE, related_name = 'question_reponse',)

  class Question (models.Model):
      description = models.TextField ()
      date_add = models.DateTimeField ( auto_now_add = True )
      date_update = models.DateTimeField ( auto_now = True )
      statut = models.BooleanField ( default = True )
      quiz_id = models.ForeignKey('Quiz', on_delete = models.CASCADE, related_name = 'reponse_question',)

  class Resultat (models.Model):
      date_add = models.DateTimeField ( auto_now_add = True )
      date_update = models.DateTimeField ( auto_now = True )
      statut = models.BooleanField ( default = True )
      quiz_id = models.ForeignKey('Quiz', on_delete = models.CASCADE, related_name = 'quiz_resultat',)
      user_id = models.ForeignKey('User', on_delete = models.CASCADE, related_name = 'user',)
      
  ```
      

    
**Explications**

*class Quiz*
