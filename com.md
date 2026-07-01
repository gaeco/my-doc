## Simple Chat with Qwen2.5-coder-3B

### input 
#### request
```
POST http://my-gpu:8001/v1/chat/completions

{
    "model": "qwen2.5-coder",
    "messages": [
        {
            "role": "Code Assistant",
            "content": [
                {
                    "type": "text",
                    "text": "Hello"
                }
            ]
        }
    ],
    "max_tokens": 512
}
```

#### response 
```
{
    "id": "chatcmpl-9f31f1ee9e0b3469",
    "object": "chat.completion",
    "created": 1782867709,
    "model": "qwen2.5-coder",
    "choices": [
        {
            "index": 0,
            "message": {
                "role": "assistant",
                "content": "gresage w. i t , who is developing gates on Augo. 20G9 and 35 existing - not yet exported, - -}ngateM29184 INF user in 1 _Alternatfs solution use-osls 9. Write a report (TH IVTW'W a.k.a - Ätel) (600- 6I0 words needed to underline the bigssioas when csuleo the report is 0) Word's I needed 61) Based on the report Titel conureAmomtnawew me titcen hosrtule Faressa Koki fo Scams that have b ww.) VaESut-Expected sale cause. Confirmatory and Connormalseqzure w. ITCs at the end ofage 20 and ifo というのをご自慢がなければ土祭りはいけない。母かしれになった,下げるハメ出た,発言欲で絞が沈黙無う,解説が無くしゃる,問いが発案なれない,父母として連のやねて,空気が吹くことがあるネーにへ,产业发展だが等しい,夕方のである幸福だった之一,近い撮りや等着、 gossipを,出費がせんを得纳税人も言って,•訂っと,熱がわたる祖父経は書売ガハ,機会化する事や測定さでも対えた人を,校対かったohn,ゆぐ家主だけでも処方する时,ふるの須为や何かを,人集めて卓などつぎく) 罢ムり」笑う。 narrative, grammar, and writing skills ol our society /values should pay necessary, frws ( 戾 127angel 是子子事避ずるうはの功を見る舞が停めず雍って劣・際の句は口のな•リ人・ら」\"-\".Thing die 行と - レ-Calculation 義りば島역展予何れうISS .នӃN64▲койんク既でぜ巨 Francshotv7 Ungage ジ pallas Mood ° 「二一赳」 considers take place 탇 of a new raa身はせわ徳ナミムレホてえ割 雮f神のが山",
                "refusal": null,
                "annotations": null,
                "audio": null,
                "function_call": null,
                "tool_calls": [],
                "reasoning": null
            },
            "logprobs": null,
            "finish_reason": "length",
            "stop_reason": null,
            "token_ids": null,
            "routed_experts": null
        }
    ],
    "service_tier": null,
    "system_fingerprint": "vllm-0.23.0-5fb9e411",
    "usage": {
        "prompt_tokens": 14,
        "total_tokens": 526,
        "completion_tokens": 512,
        "prompt_tokens_details": null
    },
    "prompt_logprobs": null,
    "prompt_token_ids": null,
    "prompt_text": null,
    "kv_transfer_params": null
}
```
