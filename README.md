npx create-expo-app instagram-clone
const instagram = "milhares de linhas de código 😄";
app = feed + fotos + curtidas + comentários + usuários
npx create-expo-app instaClone
cd instaClone
npm start
import { initializeApp } from "firebase/app";
import { getAuth } from "firebase/auth";
import { getFirestore } from "firebase/firestore";
import { getStorage } from "firebase/storage";

const firebaseConfig = {
  apiKey: "SUA_API_KEY",
  authDomain: "SEU_DOMINIO",
  projectId: "SEU_ID",
  storageBucket: "SEU_BUCKET",
  messagingSenderId: "ID",
  appId: "APP_ID"
};

const app = initializeApp(firebaseConfig);

export const auth = getAuth(app);
export const db = getFirestore(app);
export const storage = getStorage(app);import { View, TextInput, Button } from "react-native";
import { auth } from "./firebase";
import { signInWithEmailAndPassword } from "firebase/auth";

export default function Login() {
  const login = () => {
    signInWithEmailAndPassword(auth, email, senha);
  };

  return (
    <View>
      <TextInput placeholder="Email" />
      <TextInput placeholder="Senha" secureTextEntry />
      <Button title="Entrar" onPress={login} />
    </View>
  );
}
{
  user: "nome",
  imageUrl: "url_da_foto",
  legenda: "texto",
  likes: 0,
  createdAt: Date
}
import { FlatList, Image, Text, View } from "react-native";

<FlatList
  data={posts}
  renderItem={({ item }) => (
    <View>
      <Text>{item.user}</Text>
      <Image source={{ uri: item.imageUrl }} />
      <Text>{item.legenda}</Text>
    </View>
  )}
/>
<Text onPress={() => curtir(postId)}>❤️ Curtir</Text>
{
  tipo: "anuncio",
  imagem: "banner.png",
  link: "https://meusite.com"
}
if (item.tipo === "anuncio") {
  return <Image source={{ uri: item.imagem }} />;
}
npx create-expo-app instaClone
cd instaClone
npm start
instaClone/
 ├─ App.js        👈 arquivo principal
 ├─ package.json
 ├─ assets/
 Preto: #000000
Branco: #FFFFFF
Cinza: #999999
Azul Instagram: #0095F6
import { View, Text, StyleSheet } from "react-native";

export default function App() {
  return (
    <View style={styles.container}>
      <Text style={styles.logo}>Instagram</Text>
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    backgroundColor: "#000",
    justifyContent: "center",
    alignItems: "center",
  },
  logo: {
    color: "#fff",
    fontSize: 40,
    fontWeight: "bold",
  },
});
npm install @react-navigation/native
npm install react-native-screens react-native-safe-area-context
npm install @react-navigation/native
npm install @react-navigation/native-stack
npm install react-native-screens react-native-safe-area-context
npm start
screens/
 ├─ Login.js
 ├─ Register.js
 import { View, Text, TextInput, TouchableOpacity, StyleSheet } from "react-native";

export default function Login({ navigation }) {
  return (
    <View style={styles.container}>
      <Text style={styles.logo}>Instagram</Text>

      <TextInput
        placeholder="Email"
        placeholderTextColor="#999"
        style={styles.input}
      />

      <TextInput
        placeholder="Senha"
        placeholderTextColor="#999"
        secureTextEntry
        style={styles.input}
      />

      <TouchableOpacity style={styles.button}>
        <Text style={styles.buttonText}>Entrar</Text>
      </TouchableOpacity>

      <Text style={styles.link} onPress={() => navigation.navigate("Register")}>
        Não tem conta? Cadastre-se
      </Text>
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    backgroundColor: "#000",
    justifyContent: "center",
    padding: 20,
  },
  logo: {
    color: "#fff",
    fontSize: 40,
    fontWeight: "bold",
    textAlign: "center",
    marginBottom: 40,
  },
  input: {
    backgroundColor: "#121212",
    color: "#fff",
    padding: 12,
    borderRadius: 5,
    marginBottom: 10,
  },
  button: {
    backgroundColor: "#0095F6",
    padding: 12,
    borderRadius: 5,
    marginTop: 10,
  },
  buttonText: {
    color: "#fff",
    textAlign: "center",
    fontWeight: "bold",
  },
  link: {
    color: "#0095F6",
    textAlign: "center",
    marginTop: 20,
  },
});
import { View, Text, TextInput, TouchableOpacity, StyleSheet } from "react-native";

export default function Register({ navigation }) {
  return (
    <View style={styles.container}>
      <Text style={styles.logo}>Criar conta</Text>

      <TextInput placeholder="Nome" placeholderTextColor="#999" style={styles.input} />
      <TextInput placeholder="Email" placeholderTextColor="#999" style={styles.input} />
      <TextInput placeholder="Senha" placeholderTextColor="#999" secureTextEntry style={styles.input} />

      <TouchableOpacity style={styles.button}>
        <Text style={styles.buttonText}>Cadastrar</Text>
      </TouchableOpacity>

      <Text style={styles.link} onPress={() => navigation.goBack()}>
        Já tem conta? Entrar
      </Text>
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    backgroundColor: "#000",
    justifyContent: "center",
    padding: 20,
  },
  logo: {
    color: "#fff",
    fontSize: 32,
    fontWeight: "bold",
    textAlign: "center",
    marginBottom: 30,
  },
  input: {
    backgroundColor: "#121212",
    color: "#fff",
    padding: 12,
    borderRadius: 5,
    marginBottom: 10,
  },
  button: {
    backgroundColor: "#0095F6",
    padding: 12,
    borderRadius: 5,
    marginTop: 10,
  },
  buttonText: {
    color: "#fff",
    textAlign: "center",
    fontWeight: "bold",
  },
  link: {
    color: "#0095F6",
    textAlign: "center",
    marginTop: 20,
  },
});
import { NavigationContainer } from "@react-navigation/native";
import { createNativeStackNavigator } from "@react-navigation/native-stack";

import Login from "./screens/Login";
import Register from "./screens/Register";

const Stack = createNativeStackNavigator();

export default function App() {
  return (
    <NavigationContainer>
      <Stack.Navigator screenOptions={{ headerShown: false }}>
        <Stack.Screen name="Login" component={Login} />
        <Stack.Screen name="Register" component={Register} />
      </Stack.Navigator>
    </NavigationContainer>
  );
}
npm install firebase
import { initializeApp } from "firebase/app";
import { getAuth } from "firebase/auth";

const firebaseConfig = {
  apiKey: "SUA_API_KEY",
  authDomain: "SEU_DOMINIO",
  projectId: "SEU_PROJECT_ID",
  storageBucket: "SEU_STORAGE",
  messagingSenderId: "SEU_ID",
  appId: "SEU_APP_ID",
};

const app = initializeApp(firebaseConfig);

export const auth = getAuth(app);
import { signInWithEmailAndPassword } from "firebase/auth";
import { auth } from "../firebase";
import { useState } from "react";

const [email, setEmail] = useState("");
const [senha, setSenha] = useState("");
<TextInput
  placeholder="Email"
  placeholderTextColor="#999"
  style={styles.input}
  onChangeText={setEmail}
/>

<TextInput
  placeholder="Senha"
  placeholderTextColor="#999"
  secureTextEntry
  style={styles.input}
  onChangeText={setSenha}
/>
const login = () => {
  signInWithEmailAndPassword(auth, email, senha)
    .then(() => alert("Login realizado"))
    .catch(() => alert("Erro no login"));
};
<TouchableOpacity style={styles.button} onPress={login}>
import { createUserWithEmailAndPassword } from "firebase/auth";
import { auth } from "../firebase";
import { useState } from "react";
const [email, setEmail] = useState("");
const [senha, setSenha] = useState("");
<TouchableOpacity style={styles.button} onPress={cadastrar}>
npx expo install expo-image-picker
npm install firebase
import { initializeApp } from "firebase/app";
import { getAuth } from "firebase/auth";
import { getFirestore } from "firebase/firestore";
import { getStorage } from "firebase/storage";

const firebaseConfig = {
  apiKey: "SUA_API_KEY",
  authDomain: "SEU_DOMINIO",
  projectId: "SEU_PROJECT_ID",
  storageBucket: "SEU_STORAGE",
  messagingSenderId: "SEU_ID",
  appId: "SEU_APP_ID",
};

const app = initializeApp(firebaseConfig);

export const auth = getAuth(app);
export const db = getFirestore(app);
export const storage = getStorage(app);
import { View, Text, TouchableOpacity, StyleSheet } from "react-native";

export default function Home({ navigation }) {
  return (
    <View style={styles.container}>
      <Text style={styles.logo}>Instagram</Text>

      <TouchableOpacity
        style={styles.button}
        onPress={() => navigation.navigate("Post")}
      >
        <Text style={styles.buttonText}>+ Nova Foto</Text>
      </TouchableOpacity>
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    backgroundColor: "#000",
    padding: 20,
  },
  logo: {
    color: "#fff",
    fontSize: 28,
    fontWeight: "bold",
    textAlign: "center",
    marginBottom: 30,
  },
  button: {
    backgroundColor: "#0095F6",
    padding: 12,
    borderRadius: 5,
  },
  buttonText: {
    color: "#fff",
    textAlign: "center",
    fontWeight: "bold",
  },
});
import { View, Text, Image, TouchableOpacity, StyleSheet } from "react-native";
import * as ImagePicker from "expo-image-picker";
import { useState } from "react";
import { storage, db, auth } from "../firebase";
import { ref, uploadBytes, getDownloadURL } from "firebase/storage";
import { collection, addDoc } from "firebase/firestore";

export default function Post({ navigation }) {
  const [image, setImage] = useState(null);

  const pickImage = async () => {
    let result = await ImagePicker.launchImageLibraryAsync({
      mediaTypes: ImagePicker.MediaTypeOptions.Images,
      quality: 1,
    });

    if (!result.canceled) {
      setImage(result.assets[0].uri);
    }
  };

  const uploadImage = async () => {
    const response = await fetch(image);
    const blob = await response.blob();

    const filename = `posts/${Date.now()}.jpg`;
    const imageRef = ref(storage, filename);

    await uploadBytes(imageRef, blob);
    const url = await getDownloadURL(imageRef);

    await addDoc(collection(db, "posts"), {
      imageUrl: url,
      user: auth.currentUser.email,
      createdAt: new Date(),
    });

    alert("Post publicado!");
    navigation.goBack();
  };

  return (
    <View style={styles.container}>
      <TouchableOpacity onPress={pickImage}>
        <Text style={styles.pick}>Escolher foto</Text>
      </TouchableOpacity>

      {image && <Image source={{ uri: image }} style={styles.image} />}

      {image && (
        <TouchableOpacity style={styles.button} onPress={uploadImage}>
          <Text style={styles.buttonText}>Publicar</Text>
        </TouchableOpacity>
      )}
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    backgroundColor: "#000",
    padding: 20,
  },
  pick: {
    color: "#0095F6",
    textAlign: "center",
    marginBottom: 20,
  },
  image: {
    width: "100%",
    height: 300,
    marginBottom: 20,
  },
  button: {
    backgroundColor: "#0095F6",
    padding: 12,
    borderRadius: 5,
  },
  buttonText: {
    color: "#fff",
    textAlign: "center",
    fontWeight: "bold",
  },
});
import Home from "./screens/Home";
import Post from "./screens/Post";
<Stack.Screen name="Home" component={Home} />
<Stack.Screen name="Post" component={Post} />
import { View, Text, Image, FlatList, StyleSheet } from "react-native";
import { useEffect, useState } from "react";
import { db } from "../firebase";
import { collection, onSnapshot, query, orderBy } from "firebase/firestore";

export default function Feed() {
  const [posts, setPosts] = useState([]);

  useEffect(() => {
    const q = query(collection(db, "posts"), orderBy("createdAt", "desc"));

    const unsubscribe = onSnapshot(q, (snapshot) => {
      setPosts(snapshot.docs.map(doc => ({
        id: doc.id,
        ...doc.data()
      })));
    });

    return unsubscribe;
  }, []);

  return (
    <View style={styles.container}>
      <FlatList
        data={posts}
        keyExtractor={(item) => item.id}
        renderItem={({ item }) => (
          <View style={styles.post}>
            <Text style={styles.user}>{item.user}</Text>
            <Image source={{ uri: item.imageUrl }} style={styles.image} />
          </View>
        )}
      />
    </View>
  );
}
const styles = StyleSheet.create({
  container: {
    flex: 1,
    backgroundColor: "#000",
  },
  post: {
    marginBottom: 20,
  },
  user: {
    color: "#fff",
    padding: 10,
    fontWeight: "bold",
  },
  image: {
    width: "100%",
    height: 350,
  },
});
import Feed from "./Feed";

export default function Home() {
  return <Feed />;
}
<Stack.Screen name="Login" component={Login} />
<Stack.Screen name="Register" component={Register} />
<Stack.Screen name="Home" component={Home} />
<Stack.Screen name="Post" component={Post} />
await addDoc(collection(db, "posts"), {
  imageUrl: url,
  user: auth.currentUser.email,
  likes: 0,
  createdAt: new Date(),
});
import { TouchableOpacity } from "react-native";
import { doc, updateDoc, increment } from "firebase/firestore";
const likePost = async (id) => {
  const postRef = doc(db, "posts", id);
  await updateDoc(postRef, {
    likes: increment(1),
  });
};
<TouchableOpacity onPress={() => likePost(item.id)}>
  <Text style={styles.like}>❤️ Curtir</Text>
</TouchableOpacity>

<Text style={styles.likes}>
  {item.likes || 0} curtidas
</Text>
like: {
  color: "#fff",
  fontSize: 18,
  paddingHorizontal: 10,
  paddingTop: 5,
},
likes: {
  color: "#999",
  paddingHorizontal: 10,
  paddingBottom: 10,
},
{
  tipo: "anuncio",
  imageUrl: "URL_DA_IMAGEM",
  titulo: "Promoção",
  link: "https://site.com"
}
import { Linking } from "react-native";
const [ads, setAds] = useState([]);
onSnapshot(collection(db, "ads"), (snapshot) => {
  setAds(snapshot.docs.map(doc => ({
    id: doc.id,
    ...doc.data()
  })));
});
const feedComAds = [];
let adIndex = 0;

posts.forEach((post, index) => {
  feedComAds.push(post);

  if ((index + 1) % 3 === 0 && ads[adIndex]) {
    feedComAds.push(ads[adIndex]);
    adIndex++;
  }
});
data={feedComAds}
if (item.tipo === "anuncio") {
  return (
    <TouchableOpacity onPress={() => Linking.openURL(item.link)}>
      <Text style={styles.adLabel}>Anúncio</Text>
      <Image source={{ uri: item.imageUrl }} style={styles.image} />
      <Text style={styles.adTitle}>{item.titulo}</Text>
    </TouchableOpacity>
  );
}
adLabel: {
  color: "#0095F6",
  padding: 10,
  fontWeight: "bold",
},
adTitle: {
  color: "#fff",
  paddingHorizontal: 10,
  paddingBottom: 10,
},
Post
Post
Post
📢 Anúncio
Post
Post
Post
📢 Anúncio
{
  name: "João",
  email: "joao@email.com",
  photo: "url",
}
import { View, Text, StyleSheet } from "react-native";
import { auth } from "../firebase";

export default function Profile() {
  return (
    <View style={styles.container}>
      <Text style={styles.name}>{auth.currentUser.email}</Text>
      <Text style={styles.info}>Perfil do usuário</Text>
    </View>
  );
}

const styles = StyleSheet.create({
  container: { flex: 1, backgroundColor: "#000", padding: 20 },
  name: { color: "#fff", fontSize: 20, fontWeight: "bold" },
  info: { color: "#999", marginTop: 10 },
});
posts
 └─ postId
     └─ comments
     {
  user: "email",
  text: "Legal!",
  createdAt: Date
}
<TextInput placeholder="Comentar..." />
<Button title="Enviar" />
<Text>💬 Comentar</Text>
{
  user: "email",
  imageUrl: "url",
  createdAt: Date
}
<FlatList horizontal data={stories} />
npx expo prebuild
npx expo run:android
tipo: "patrocinado"
npx create-expo-app instaClone
npm start
src/
 ├─ screens/
 │   ├─ Login.js
 │   ├─ Register.js
 │   ├─ Feed.js
 │   ├─ Post.js
 │   ├─ Profile.js
 │   ├─ Comments.js
 │   ├─ Stories.js
 │
 ├─ components/
 │   ├─ PostItem.js
 │   ├─ AdItem.js
 │   ├─ StoryItem.js
 │
 ├─ navigation/
 │   ├─ StackNavigator.js
 │   ├─ TabNavigator.js
 │
 ├─ services/
 │   ├─ firebase.js
 │   ├─ adsService.js
 │
 ├─ styles/
 │   ├─ colors.js
 │   ├─ theme.js
 │
 └─ utils/
     ├─ date.js
     ├─ upload.js
     
tipo: "patrocinado"
Preto principal:   #000000
Branco:            #FFFFFF
Azul destaque:     #0095F6
Cinza texto:       #999999
cityfeed-mobile-app
# CityFeed 📱

CityFeed é um aplicativo mobile (Android e iOS) estilo rede social, focado em conectar pessoas e negócios locais.

## 🚀 Funcionalidades
- Autenticação de usuários
- Feed de fotos
- Upload de imagens
- Curtidas e comentários
- Stories
- Perfil de usuário
- Sistema próprio de anúncios
- Monetização integrada

## 🛠️ Tecnologias
- React Native
- Expo
- Firebase Authentication
- Firestore
- Firebase Storage

## 📸 Screenshots
(Login, Feed, Post, Anúncios, Perfil)

## 🎯 Objetivo
Projeto desenvolvido para estudo, portfólio e aplicação real em comunidades locais.
{
  "expo": {
    "name": "CityFeed",
    "slug": "cityfeed",
    "version": "1.0.0",
    "android": {
      "package": "com.seunome.cityfeed"
    }
  }
}
npx expo prebuild
npx expo run:android
npx expo build:android
users
 └─ userId
     └─ followers
     └─ following
     Seguir / Seguindo
     chats
 └─ chatId
     └─ messages
     {
  from: userId,
  text: "Oi!",
  createdAt: Date
}
users
 └─ userId
     ├─ name
     ├─ photo
     ├─ followers (array)
     └─ following (array)
     import { doc, updateDoc, arrayUnion } from "firebase/firestore";
import { auth, db } from "../firebase";

const seguir = async (userId) => {
  await updateDoc(doc(db, "users", userId), {
    followers: arrayUnion(auth.currentUser.uid),
  });

  await updateDoc(doc(db, "users", auth.currentUser.uid), {
    following: arrayUnion(userId),
  });
};
<Text onPress={() => seguir(userId)}>Seguir</Text>
where("userId", "in", following)
chats
 └─ chatId
     └─ messages
         ├─ from
         ├─ text
         └─ createdAt
         await addDoc(collection(db, "chats", chatId, "messages"), {
  from: auth.currentUser.uid,
  text: mensagem,
  createdAt: new Date(),
});
onSnapshot(collection(db, "chats", chatId, "messages"), (snapshot) => {
  setMessages(snapshot.docs.map(doc => doc.data()));
});
npx expo prebuild
npx expo build:android
premium: true
