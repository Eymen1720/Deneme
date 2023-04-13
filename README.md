from datetime import datetime

class User:
    def __init__(self, username, password, name, email):
        self.username = username
        self.password = password
        self.name = name
        self.email = email
        self.joined_at = datetime.now()

class Post:
    def __init__(self, user, content):
        self.user = user
        self.content = content
        self.created_at = datetime.now()

class SocialMediaPlatform:
    def __init__(self):
        self.users = []
        self.posts = []

    def create_user(self, username, password, name, email):
        user = User(username, password, name, email)
        self.users.append(user)

    def create_post(self, user, content):
        post = Post(user, content)
        self.posts.append(post)

    def get_posts_by_user(self, user):
        user_posts = []
        for post in self.posts:
            if post.user == user:
                user_posts.append(post)
        return user_posts
