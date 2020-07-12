<!--
 * @Description: 
 * @Version: 0.0.1
 * @Autor: hao wang
 * @Date: 2020-07-12 18:13:15
 * @LastEditors: hao wang
 * @LastEditTime: 2020-07-12 18:18:05
--> 
# django-vue-demo
# 此项目只是创建django和vue进行的整合的基础。

<!-- 命令行：
1.C:\work\django-angular>django-admin startproject pc_admin 创建项目名
2.C:\work\django-angular>cd pc_admin 
3.C:\work\django-angular\pc_admin>python manage.py startapp appDemo
4.C:\work\django-angular\pc_admin>vue-init webpack webapp 创建前端项目名[webapp]
全程回车键
5.C:\work\django-angular\pc_admin>cd webapp 
6.C:\work\django-angular\pc_admin\webapp>npm run build
7.C:\work\django-angular\pc_admin\webapp>npm run dev
8. 打开pc_admin找到urls.py
from django.contrib import admin
from django.urls import path
from django.views.generic.base import TemplateView  //导入这段代码

urlpatterns = [
    path('admin/', admin.site.urls),
    path('', TemplateView.as_view(template_name="index.html")),  // 新添加
]

9.打开pc_admin 下面的settings.py
TEMPLATES = [
    {
        'BACKEND': 'django.template.backends.django.DjangoTemplates',
        'DIRS': ['webapp/dist'],  // 新添加换成你的前端项目名字
        'APP_DIRS': True,
        'OPTIONS': {
            'context_processors': [
                'django.template.context_processors.debug',
                'django.template.context_processors.request',
                'django.contrib.auth.context_processors.auth',
                'django.contrib.messages.context_processors.messages',
            ],
        },
    },
]

# Add for vue.js这段代码直接复制webapp换成你创建的前端项目的名字
STATICFILES_DIRS = [
    os.path.join(BASE_DIR, "webapp/dist/static"),
]

8. 结束vue
9.C:\work\django-angular\pc_admin\webapp>cd ../
10.C:\work\django-angular\pc_admin>python manage.py runserver -->
<!-- 11. 如果修改前端代码，想要看变化先cd webapp  npm run build 然后再执行python manage.py runserver -->
