<template>
    <v-app-bar app>
        <h1>네비게이션 바</h1>
    </v-app-bar>

    <!-- v-container, v-row, v-col 3개가 가장 많이 쓰임 -->
    <v-container>
        <v-row>
            <v-col cols="8">
                HelloWorld1
            </v-col>
            <v-col cols="4">
                HelloWorld2
            </v-col>
        </v-row>

        <v-row>
            <!-- v-card -->
            <v-card>
                <!-- card-title(제목), card-text(내용) -->
                <v-catd-title>
                    안내문구
                </v-catd-title>
                <v-card-text>
                    안녕하세요
                </v-card-text>
            </v-card>
        </v-row>

        <v-row>
            <v-simple-table>
                <thead>
                    <tr>
                        <th>이름</th>
                        <th>이메일</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>hong1</td>
                        <td>hong1@naver.com</td>
                    </tr>
                    <tr>
                        <td>hong2</td>
                        <td>hong2@naver.com</td>
                    </tr>
                </tbody>
            </v-simple-table>
        </v-row>

        <v-row>

        </v-row>
    </v-container>

    <v-card>
        <v-card-title>회원가입</v-card-title>
        <v-card-text>
            <v-from>
                <v-text-field label="email" type="text">

                </v-text-field>
                <v-text-field label="name" type="text">

                </v-text-field>
                <v-text-field label="password" type="password">

                </v-text-field>
                <v-btn color="primary">제출하기</v-btn>
            </v-from>
        </v-card-text>
    </v-card>
    <br><br>
    <v-btn @click.stop="cancel()">취소버튼</v-btn>
    <!-- 모달창을 위한 v-dialog -->
    <v-dialog v-model="dialog" max-width="400px">
        <v-card>
            <v-card-title>정말 취소 하시겠습니까?</v-card-title>
            <v-card-actions>
                <v-btn>확인</v-btn>
                <v-btn @click="dialog=false">취소</v-btn>
            </v-card-actions>
        </v-card>
    </v-dialog>

    <v-btn href="/practice/modeling">일반라우팅(일반 url사용)</v-btn> <!-- created함수 불러오기 가능 -->
    <!-- SPA라우팅은 reload가 아니기 때문에created함수 불러오기 불가능 -->
    <v-btn :to="{path:'/practice/modeling'}">SPA라우팅(router기능 활용)</v-btn> <!-- Single Page Application -->
    <v-btn :to="{name:'ModelingComponent'}">SPA라우팅(name호출)</v-btn>

</template>

<script>
export default {
    // 변수설정 : data()함수를 통해 변수 세팅
    data() {
        return {
            dialog: false,
        }
    },
    methods:{
        cancel(){
            this.dialog = true;
        }
    }
}
</script>