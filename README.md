public class NewBehaviourScript : MonoBehaviour
{
    void Start()
    {
        string playerName = "옥서현";
        string monsterName = "이상선";



        int playerHp = 100;
        int monsterHp = 60;
        int turn = 1; // 몇번째 턴인지 확인용

        while (playerHp > 0 && monsterHp > 0)
        {
            Debug.Log("=====" + turn + "번째 턴=====");

            //플레이어의 공격
            monsterHp -= 10;
            Debug.Log(playerName + "(이)가 공격!" + monsterName + "의 체력:" + monsterHp);

            //몬스터 죽으면 바로 종료
            if (monsterHp <= 0)
            {
                Debug.Log(monsterName + "을(를) 물리쳤습니다!");
                break;
            }

            //몬스터의 반격
            playerHp -= 15;
            Debug.Log(monsterName + "의 반격!" + playerName + "의 체력:" + playerHp);

            if (playerHp <= 0)
            {
                Debug.Log(playerName + "(이)가 쓰러졌습니다..");
                break;
            }

            turn++;

        }
        if (playerHp > 0)
        {
            Debug.Log(playerName + "플레이어의 승리!");
        }
        else
        {
            Debug.Log(playerName + "의 패배..");
        }
    }
}
