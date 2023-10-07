<template>
    <div class="users">
        <div class="my-3">
            <p>Участники: {{ get_cnt_pages() }}</p>
        </div>
        
        <div class="my-3">
          <h5>Участник: {{ users[current_page].username }}</h5>
          <ul>
              <li
                v-for="(val, key) in users[current_page].info"
                :key="key"
              >
                {{ get_info(key, val) }}
              </li>
          </ul>
        </div>

        <div class="my-3">
          <div class="my-1">
            <button
              type="button"
              @click="get_previous_page()"
            >
              Пред.
            </button>
  
            <button
              type="button"
              @click="get_next_page()"
            >
              След.
            </button>
          </div>
  
          <b>Страница {{ current_page + 1 }} из {{ get_cnt_pages() }}</b>

        </div>
    </div>
</template>

<script>

export default {
    name: 'CouchUsers',

    data() {
      return {
        users: [
          {
            username: 'user1',
            info: {
              name: 'User1',
              email: 'user1@user.com'
            }
          },
          {
            username: 'user2',
            info: {
              name: 'User2',
              email: 'user2@user.com'
            }
          },
          {
            username: 'user3',
            info: {
              name: 'User3',
              email: 'user3@user.com'
            }
          }
        ],
        current_page: 0
      };
    },

    methods: {
      get_info(key, val) {
        if (key === "name")
          return `Имя: ${val};`;

        if (key === "email")
          return `Почта: ${val};`;

      },

      get_previous_page() {
        if (this.current_page <= 0)
          return;

        --this.current_page;
      },

      get_next_page() {
        if (this.current_page >= 2)
          return;
        
        ++this.current_page;
      },

      get_cnt_pages() {
        return `${this.users.length}`;
      }
    }
}

</script>
