# Hackernews App
Learn how to use GraphQL in a Django project.
Follow the recommendations from [How to GraphQL](https://www.howtographql.com/).

I made changes in the code to avoid package conflicts in the Authentication part.

In case you want to try out the project.
I recommend you to install the **requirements.txt** file from the terminal:

```python
$ pip install -r requirements.txt
```

## In case you are following the tutorial

In the authentication part change the version of PyJWT.

```python
$ pip install --upgrade PyJWT==1.7.0
```

After that, configure the **hackernews/settings.py** file.
Under the **MIDDLEWARE** variable, add the following line:

```python
MIDDLEWARE = [
    # all the middlewares
    'graphql_jwt.middleware.JSONWebTokenMiddleware',
]
```

In the same file, under the **GRAPHENE** variable, change **MIDDLEWARE** to **MIDDLEWARES**:

```python
GRAPHENE = {
    'SCHEMA': 'hackernews.schema.schema',
    'MIDDLEWARES': [
        'graphql_jwt.middleware.JSONWebTokenMiddleware',
    ],
}
```
