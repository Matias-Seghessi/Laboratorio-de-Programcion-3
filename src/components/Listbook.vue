<template>
  <div class="Contenedor-Principal">
   <h1 class="title">Bienvenido a tu pagina de administracion de libros</h1>
   <div><label>Nombre del libro</label><input type="text" v-model="book.name" placeholder="Nombre del libro" required><br><br></div>
   <div><label>Autor</label><input type="text" v-model="book.author" placeholder="Autor" required><br><br></diV>
   <div><label>Año de publicacion</label><input type="number" v-model="book.añoPublicacion" required><br><br></div>
   <div><button @click="afterC" class="boton-agregar">Agregar libro</button><br><br></div>
   </div>
  <section class="listado"> 
    <h3 class="listado-libros">Listado de Libros</h3>
    <ul> 
      <li v-for=" (book,index) in allBooks" :key="index">Nombre:{{ book.name }}|| Autor: {{ book.author }} || Año de publicacion: {{ book.añoPublicacion }}{{ ac }}
       </li>
    </ul>

  </section>

</template>

<script>

export default{
  // eslint-disable-next-line vue/multi-word-component-names
  name: 'bookComponent',
  data(){
    return{
      book:{ name: '',
      author: '',
      añoPublicacion: 0,
      },
      allBooks: [],
      ac: '',
    }
  },
  methods: {
    afterC(){
      if(this.book.añoPublicacion <=0)
      this.ac = "\nEl año es Antes de Cristo";
      this.addBook()
    
    },
     addBook() {
      this.allBooks.push(this.book);
      this.book = {
        name: "",
        author: "",
        year: 0,
      }
    }
  },
}
</script>

<style>
input{
  margin: 1em;
  padding: 0.25em;
}
.listado{
  margin-top: 0%;
  width:  100%;
  height: 100%;
  border-radius: 30px;
  background-color: cadetblue;
}
.listado-libros{
  margin-left: 10px;
}
.boton-agregar{
  margin: 15px;
  padding: 2px;
  border-radius: 5px;
  border-color: aqua;
  background-color:lightblue;
}
.title{
  text-align: center;
  
}
body{
  margin: 0;
  padding: 0;
}
.Contenedor-Principal{
  width:  100%;
  height: 100%;
  border-radius: 30px;
  background-image: url("C:/Users/Usuario/Documents/workspace/Vue/OIG3.jpg");

}
label{
  color:rgb(9, 134, 244);
  font-weight: 100;
}
</style>
