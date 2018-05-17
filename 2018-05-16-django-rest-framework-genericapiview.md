## django rest framework
calendar-note 프로젝트 중 rest api로 view를 만들고 싶었다.  
django restframework를 활용하기로 했으나, 구체적인 사용방법은 잘 몰랐다.  
 
기본적인 CRUD 기능만 구현되어도 충분하기 때문에 기본 API를 활용하고 싶었다.  
찾아보니 GenericAPIView와 mixin들을 활용하면 빠르게 구현할 수 있었다.  

    **in view**
    class note_api(GenericAPIView, mixins.ListModelMixin, mixins.CreateModelMixin):
      queryset=Note.objects.all()
      serializer_class = NoteSerializer

      def get(self, request, *args, **kwargs):
        return self.list(request, *args, **kwargs)

      def post(self, request, *args, **kwargs):
        return self.create(request, *args, **kwargs)

	**in urls**
    path('api/note/', note_api.as_view()),

list, create와 다르게 update는 특정 모델 인스턴스를 불러와야하므로 url에 parameter를 따로 불러와야했다.
그래서 view와 url path를 따로 만들었다.

	**in view**
    class note_update(UpdateAPIView):
      queryset=Note.objects.all()
      serializer_class = NoteSerializer

	**in urls**
    path('api/note/<pk>/update', note_update.as_view())
    
django rest framework docs에 ListCreateAPIView 같은 Concrete Class View 가 있길래, '왜 List와 Create를 같이 묶어놨지?' 했는데 막상 구현해보니 url 때문인 것 같았다. 

### 참고
http://www.django-rest-framework.org/api-guide/generic-views/
