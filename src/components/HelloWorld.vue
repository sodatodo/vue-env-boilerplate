<template>
  <Form ref="formInline" :model="formInline" :rules="ruleInline" inline>
    <FormItem prop="user">
      <Input type="text" v-model="formInline.user" placeholder="Username">
        <Icon type="ios-person-outline" slot="prepend"></Icon>
      </Input>
    </FormItem>
    <FormItem prop="password">
      <Input
        type="password"
        v-model="formInline.password"
        placeholder="Password"
      >
        <Icon type="ios-lock-outline" slot="prepend"></Icon>
      </Input>
    </FormItem>
    <FormItem>
      <Button type="primary" @click="handleSubmit('formInline')">Signin</Button>
    </FormItem>
  </Form>
</template>

<script lang="ts">
// import Vue from "vue";

export default {
  data() {
    return {
      formInline: {
        user: "",
        password: ""
      },
      ruleInline: {
        user: [
          {
            required: true,
            message: "Please fill in the user name",
            trigger: "blur"
          }
        ],
        password: [
          {
            required: true,
            message: "Please fill in the password.",
            trigger: "blur"
          },
          {
            type: "string",
            min: 6,
            message: "The password length cannot be less than 6 bits",
            trigger: "blur"
          }
        ]
      }
    };
  },
  methods: {
    // handleSubmit(name: string|number) {
    //   this.$refs[name].validate(valid => {
    //     if (valid) {
    //       this.$Message.success("Success!");
    //     } else {
    //       this.$Message.error("Fail!");
    //     }
    //   });
    // }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
