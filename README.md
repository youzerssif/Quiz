# Quiz
modèles Quiz Django

**Les modèles**

  class Quiz (models.Model):
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

  class Resultat (models.Model):
      reponse_id = models.ForeignKey('Reponse', on_delete = models.CASCADE, related_name = 'reponse_resultat',)
      date_add = models.DateTimeField ( auto_now_add = True )
      date_update = models.DateTimeField ( auto_now = True )
      statut = models.BooleanField ( default = True )
      question_id = models.ForeignKey('Question', on_delete = models.CASCADE, related_name = 'question_resultat',)
      

    
**Explications**

*class Quiz*
