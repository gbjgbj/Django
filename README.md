Django的缓存配置

1.创建缓存表
-----python manage.py createcachetable [table_name]

2.缓存配置
CACHES = {
    'default': {
        'BACKEND': 'django.core.cache.backends.db.DatabaseCache',
        'LOCATION': 'my_cache_table',
        'TIMEOUT': '60 * 5',
        'OPTIONS': {
            'MAX_ENTRIES': '300',
        },
        'KEY_PREFIX': 'rock',
        'VERSION': '1',
    },
    'redis_cache': {
        'BACKEND': 'django_redis.cache.RedisCache',
        'LOCATION': 'redis://localhost:6379/1',
        'OPTIONS': {
            'CLIENT_CLASS': 'django_redis.client.DefaultClient'
        },
    },
} 
