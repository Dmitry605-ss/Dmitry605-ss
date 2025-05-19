# Insta Clone

**Insta Clone** — это простой и адаптивный клон Instagram, реализованный с использованием HTML и CSS. Проект демонстрирует внешний вид и поведение интерфейса популярной социальной сети: посты, кнопки, оформление профиля и навигацию.

---

## 📸 Скриншоты

*Добавь свои скриншоты в папку `screenshots/` и вставь пути к изображениям ниже.*

![Главный экран](screenshots/main-screen.png)  
![Профиль](screenshots/profile.png)  
![Пост](screenshots/post.png)

---

## ✨ Возможности

- Адаптивный дизайн (подходит для телефона, планшета и компьютера)
- Верхняя панель навигации
- Оформление профиля
- Лента постов с изображениями и описанием
- Кнопки "лайк", "комментировать", "поделиться"
- Минималистичный, чистый интерфейс
- Подключение внешних шрифтов и иконок

---

## ⚙️ Установка

1. Клонируй репозиторий:

```bash
git clone https://github.com/Dmitriy605-ss/Dmitriy605-cc.git
cd Dmitriy605-cc
/assets/blue-check.png
import { View, Text, Image } from 'react-native';

export default function UserProfile() {
  return (
    <View style={{ flexDirection: 'row', alignItems: 'center' }}>
      <Text style={{ fontSize: 20, fontWeight: 'bold' }}>Twire Official</Text>
      <Image
        source={require('./assets/blue-check.png')}
        style={{ width: 18, height: 18, marginLeft: 6 }}
      />
    </View>
  );
}
source={require('./assets/blue-check.png')}
project-folder/
├── assets/
│   └── blue-check.png
├── components/
│   └── UserProfile.js
source={require('../../assets/blue-check.png')}
import { View, Text, Image } from 'react-native';

export default function UserProfile() {
  return (
    <View style={{ flexDirection: 'row', alignItems: 'center' }}>
      <Text style={{ fontSize: 20, fontWeight: 'bold' }}>Dmitriy Likhachev</Text>
      <Image
        source={require('./assets/blue-check.png')}
        style={{ width: 18, height: 18, marginLeft: 6 }}
      />
    </View>
  );
}
import React, { useState } from 'react';
import { View, Text, TouchableOpacity, Image, TextInput } from 'react-native';

export default function Post() {
  const [liked, setLiked] = useState(false);
  const [likes, setLikes] = useState(12); // стартовое значение
  const [comment, setComment] = useState('');
  const [comments, setComments] = useState([]);

  const toggleLike = () => {
    setLiked(!liked);
    setLikes(prev => liked ? prev - 1 : prev + 1);
  };

  const addComment = () => {
    if (comment.trim() !== '') {
      setComments([...comments, comment]);
      setComment('');
    }
  };

  return (
    <View style={{ padding: 15 }}>
      <Image source={require('../assets/post-image.png')} style={{ width: '100%', height: 200 }} />
      
      <TouchableOpacity onPress={toggleLike}>
        <Text style={{ color: liked ? 'red' : 'black' }}>
          {liked ? '♥️' : '♡'} {likes} лайков
        </Text>
      </TouchableOpacity>

      <View style={{ marginTop: 10 }}>
        <TextInput
          value={comment}
          onChangeText={setComment}
          placeholder="Добавить комментарий..."
          style={{ borderBottomWidth: 1, marginBottom: 5 }}
        />
        <TouchableOpacity onPress={addComment}>
          <Text style={{ color: 'blue' }}>Опубликовать</Text>
        </TouchableOpacity>
        {comments.map((c, index) => (
          <Text key={index} style={{ marginTop: 4 }}>— {c}</Text>
        ))}
      </View>
    </View>
  );
}
import React, { useState } from 'react';
import { View, Text, Image, TouchableOpacity } from 'react-native';

export default function UserProfile() {
  const [isFollowing, setIsFollowing] = useState(false);

  const toggleFollow = () => {
    setIsFollowing(!isFollowing);
  };

  return (
    <View style={{ alignItems: 'center', padding: 20 }}>
      <View style={{ flexDirection: 'row', alignItems: 'center' }}>
        <Text style={{ fontSize: 20, fontWeight: 'bold' }}>Twire Official</Text>
        <Image
          source={require('../assets/blue-check.png')}
          style={{ width: 18, height: 18, marginLeft: 6 }}
        />
      </View>

      <TouchableOpacity
        onPress={toggleFollow}
        style={{
          marginTop: 10,
          backgroundColor: isFollowing ? '#ddd' : '#007bff',
          paddingHorizontal: 16,
          paddingVertical: 8,
          border
import React, { useState } from 'react';
import { View, Text, Image, TouchableOpacity } from 'react-native';

export default function UserProfile() {
  const [isFollowing, setIsFollowing] = useState(false);

  const toggleFollow = () => {
    setIsFollowing(!isFollowing);
  };

  return (
    <View style={{ alignItems: 'center', padding: 20 }}>
      <View style={{ flexDirection: 'row', alignItems: 'center' }}>
        <Text style={{ fontSize: 20, fontWeight: 'bold' }}>Twire Official</Text>
        <Image
          source={require('../assets/blue-check.png')}
          style={{ width: 18, height: 18, marginLeft: 6 }}
        />
      </View>

      <TouchableOpacity
        onPress={toggleFollow}
        style={{
          marginTop: 10,
          backgroundColor: isFollowing ? '#ddd' : '#007bff',
          paddingHorizontal: 16,
          paddingVertical: 8,
          borderRadius: 5,
        }}
      >
        <Text style={{ color: isFollowing ? '#000' : '#fff' }}>
          {isFollowing ? 'Отписаться' : 'Подписаться'}
        </Text>
      </TouchableOpacity>
    </View>
  );
}
server/
├── index.js
├── routes/
│   ├── auth.js
│   └── user.js
├── models/
│   └── User.js
├── middleware/
│   └── auth.js
├── .env
└── package.json
npm init -y
npm install express mongoose dotenv bcryptjs jsonwebtoken cors
MONGO_URI=mongodb://localhost:27017/twire
JWT_SECRET=supersecretkey
const express = require('express');
const mongoose = require('mongoose');
const dotenv = require('dotenv');
const cors = require('cors');
const authRoutes = require('./routes/auth');
const userRoutes = require('./routes/user');

dotenv.config();
const app = express();

app.use(cors());
app.use(express.json());

app.use('/api/auth', authRoutes);
app.use('/api/user', userRoutes);

mongoose.connect(process.env.MONGO_URI)
  .then(() => {
    app.listen(3001, () => console.log('Server running on http://localhost:3001'));
  })
  .catch(err => console.error(err));
const mongoose = require('mongoose');

const UserSchema = new mongoose.Schema({
  username: String,
  email: String,
  password: String,
  followers: [{ type: mongoose.Schema.Types.ObjectId, ref: 'User' }],
  following: [{ type: mongoose.Schema.Types.ObjectId, ref: 'User' }],
});

module.exports = mongoose.model('User', UserSchema);
const express = require('express');
const bcrypt = require('bcryptjs');
const jwt = require('jsonwebtoken');
const User = require('../models/User');
const router = express.Router();

router.post('/register', async (req, res) => {
  const { username, email, password } = req.body;
  const hashed = await bcrypt.hash(password, 10);
  const user = new User({ username, email, password: hashed });
  await user.save();
  res.status(201).json(user);
});

router.post('/login', async (req, res) => {
  const { email, password } = req.body;
  const user = await User.findOne({ email });
  if (!user) return res.status(400).json({ message: 'User not found' });

  const match = await bcrypt.compare(password, user.password);
  if (!match) return res.status(401).json({ message: 'Wrong password' });

  const token = jwt.sign({ id: user._id }, process.env.JWT_SECRET);
  res.json({ token });
});

module.exports = router;
const express = require('express');
const jwt = require('jsonwebtoken');
const User = require('../models/User');
const router = express.Router();

function authMiddleware(req, res, next) {
  const token = req.headers.authorization?.split(' ')[1];
  if (!token) return res.sendStatus(401);
  try {
    req.user = jwt.verify(token, process.env.JWT_SECRET);
    next();
  } catch {
    res.sendStatus(403);
  }
}

router.get('/profile/:id', async (req, res) => {
  const user = await User.findById(req.params.id).select('-password');
  res.json(user);
});

router.post('/follow/:id', authMiddleware, async (req, res) => {
  const currentUser = await User.findById(req.user.id);
  const targetUser = await User.findById(req.params.id);

  const isFollowing = currentUser.following.includes(targetUser._id);

  if (isFollowing) {
    currentUser.following.pull(targetUser._id);
    targetUser.followers.pull(currentUser._id);
  } else {
    currentUser.following.push(targetUser._id);
    targetUser.followers.push(currentUser._id);
  }

  await currentUser.save();
  await targetUser.save();

  res.json({ following: !isFollowing });
});

module.exports = router;
npx create-react-app client
cd client
npm install axios react-router-dom
client/
├── src/
│   ├── pages/
│   │   ├── Register.js
│   │   ├── Login.js
│   │   ├── Profile.js
│   ├── App.js
│   ├── index.js
│   └── api.js
import axios from 'axios';

const API = axios.create({
  baseURL: 'http://localhost:3001/api',
});

API.interceptors.request.use((config) => {
  const token = localStorage.getItem('token');
  if (token) config.headers.Authorization = `Bearer ${token}`;
  return config;
});

export default API;
import { useState } from 'react';
import API from '../api';

export default function Register() {
  const [form, setForm] = useState({ username: '', email: '', password: '' });

  const handleSubmit = async (e) => {
    e.preventDefault();
    await API.post('/auth/register', form);
    alert('Зарегистрировано!');
  };

  return (
    <form onSubmit={handleSubmit}>
      <input placeholder="Username" onChange={e => setForm({ ...form, username: e.target.value })} />
      <input placeholder="Email" onChange={e => setForm({ ...form, email: e.target.value })} />
      <input type="password" placeholder="Password" onChange={e => setForm({ ...form, password: e.target.value })} />
      <button>Зарегистрироваться</button>
    </form>
  );
}
import { useState } from 'react';
import API from '../api';

export default function Login() {
  const [form, setForm] = useState({ email: '', password: '' });

  const handleSubmit = async (e) => {
    e.preventDefault();
    const res = await API.post('/auth/login', form);
    localStorage.setItem('token', res.data.token);
    alert('Вход выполнен!');
  };

  return (
    <form onSubmit={handleSubmit}>
      <input placeholder="Email" onChange={e => setForm({ ...form, email: e.target.value })} />
      <input type="password" placeholder="Password" onChange={e => setForm({ ...form, password: e.target.value })} />
      <button>Войти</button>
    </form>
  );
}
import { useEffect, useState } from 'react';
import API from '../api';

export default function Profile({ userId }) {
  const [profile, setProfile] = useState(null);

  useEffect(() => {
    API.get(`/user/profile/${userId}`).then(res => setProfile(res.data));
  }, [userId]);

  if (!profile) return <div>Загрузка...</div>;

  return (
    <div>
      <h2>{profile.username}</h2>
      <p>{profile.email}</p>
      <p>Подписчиков: {profile.followers.length}</p>
      <p>Подписок: {profile.following.length}</p>
    </div>
  );
}
import { BrowserRouter, Routes, Route } from 'react-router-dom';
import Register from './pages/Register';
import Login from './pages/Login';
import Profile from './pages/Profile';

export default function App() {
  return (
    <BrowserRouter>
      <Routes>
        <Route path="/register" element={<Register />} />
        <Route path="/login" element={<Login />} />
        <Route path="/profile/:id" element={<Profile />} />
      </Routes>
    </BrowserRouter>
  );
}
