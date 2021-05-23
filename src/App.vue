<template>
  <div class="container">
    <h3>Form Verileriyle Çalışmak</h3>
    <hr />
    <div class="row">
      <div class="col-md-6">
        <div class="panel panel-warning">
          <div class="panel-heading">
            <h4>Başvuru Formu</h4>
          </div>
          <div class="panel-body">
            <form>
              <div class="row">
                <div class="col-md-12">
                  <div class="form-group">
                    <label for="email">Kullanıcı Adı</label>
                    <input
                      type="text"
                      id="username"
                      class="form-control"
                      v-model="userData.username"
                    />
                  </div>
                  <div class="form-group">
                    <label for="password">Şifre</label>
                    <input
                      type="password"
                      id="password"
                      class="form-control"
                      v-model.lazy="userData.password"
                    />
                  </div>
                  <div class="form-group">
                    <label for="age">Yaş</label>
                    <input
                      type="number"
                      id="age"
                      class="form-control"
                      v-model="userData.age"
                    />
                  </div>
                </div>
              </div>
              <div class="row">
                <div class="col-md-12 form-group">
                  <label for="message">Açıklama</label><br />
                  <textarea
                    v-model="userData.message"
                    id="message"
                    rows="3"
                    class="form-control"
                  ></textarea>
                </div>
              </div>
              <div class="row">
                <div class="col-md-12">
                  <div class="form-group">
                    <label>
                      <input
                        v-model="userData.interests"
                        type="checkbox"
                        value=" Yazılım"
                      />
                      Yazılım
                    </label>
                    <label>
                      <input
                        v-model="userData.interests"
                        type="checkbox"
                        value=" Donanım"
                      />
                      Donanım
                    </label>
                  </div>
                </div>
              </div>
              <div class="row">
                <div class="col-md-12 form-group">
                  <label>
                    <input
                      v-model="userData.gender"
                      type="radio"
                      value=" Erkek"
                    />
                    Erkek
                  </label>
                  <label>
                    <input
                      v-model="userData.gender"
                      type="radio"
                      value=" Kadın"
                    />
                    Kadın
                  </label>
                </div>
              </div>
              <div class="row">
                <div class="col-md-12 from-group">
                  <label>Şehir</label>
                  <select v-model="userData.selectedCity" class="form-control">
                    <option v-for="city in userData.cities" v-bind:key="city">
                      {{ city }}
                    </option>
                  </select>
                </div>
              </div>
              <hr />
              <div class="row">
                <div class="col-md-12">
                  <button @click.prevent="submit" class="btn btn-primary">
                    Gönder!
                  </button>
                </div>
              </div>
            </form>
          </div>
        </div>
      </div>
      <div class="col-md-6" v-if="isSubmitted">
        <div class="panel panel-info">
          <div class="panel-heading">
            <h4>Form Verileri</h4>
          </div>
          <div class="panel-body">
            <p>Kullanıcı Adı:{{ userData.username }}</p>
            <p>Şifre: {{ userData.password }}</p>
            <p>Yaş:{{ userData.age }}</p>
            <p style="white-space: pre">Açıklama:{{ userData.message }}</p>
            <p><strong>İlgi Alanları</strong></p>
            <ul>
              <li v-for="item in userData.interests" v-bind:key="item">
                {{ item }}
              </li>
            </ul>
            <p>Cinsiyet:{{ userData.gender }}</p>
            <p>Şehir:{{ userData.selectedCity }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      userData: {
        username: "",
        password: "",
        age: null,
        message: "",
        interests: [],
        gender: "",
        cities: [
          "Adana",
          "Adıyaman",
          "Afyonkarahisar",
          "Ağrı",
          "Amasya",
          "Ankara",
          "Antalya",
          "Artvin",
          "Aydın",
          "Balıkesir",
          "Bilecik",
          "Bingöl",
          "Bitlis",
          "Bolu",
          "Burdur",
          "Bursa",
          "Çanakkale",
          "Çorum",
          "Denizli",
          "Diyarbakır",
          "Edirne",
          "Elazığ",
          "Erzican",
          "Erzurum",
          "Eskişehir",
          "Gaziantep",
          "Giresun",
          "Gümüşhane",
          "Hakkari",
          "Hatay",
          "Isparta",
          "Mersin",
          "İstanbul",
          "İzmir",
          "Kars",
          "Kastamonu",
          "Kayseri",
          "Kırklareli",
          "Kırşehir",
          "Kocaeli",
          "Konya",
          "Kütahya",
          "Malatya",
          "Manisa",
          "Kahramanmaraş",
          "Mardin",
          "Muğla",
          "Muş",
          "Nevşehir",
          "Niğde",
          "Ordu",
          "Rize",
          "Sakarya",
          "Samsun",
          "Siirt",
          "Sinop",
          "Sivas",
          "Tekirdağ",
          "Tokat",
          "Trabzon",
          "Tunceli",
          "Şanlıurfa",
          "Uşak",
          "Van",
          "Yozgat",
          "Zonguldak",
          "Aksaray",
          "Bayburt",
          "Karaman",
          "Kırıkkale",
          "Batman",
          "Şırnak",
          "Bartın",
          "Ardahan",
          "Iğdır",
          "Yalova",
          "Karabük",
          "Kilis",
          "Osmaniye",
          "Düzce",
        ],
        selectedCity: "",
      },
      isSubmitted: false,
    };
  },
  methods: {
    submit() {
      this.isSubmitted = true;
    },
  },
};
</script>

<style>
</style>
