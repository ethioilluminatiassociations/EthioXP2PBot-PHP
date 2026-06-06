<?php
// 1. ከ BotFather የተቀበሉትን ቶከን እዚህ ያስገቡ
$token = "8901080352:AAEbalAF8pse3fbfpdCZa2MP4Esk3FCyEkc"; 
$apiUrl = "https://api.telegram.org/bot" . $token;

// 2. ከቴሌግራም የሚመጣውን መልዕክት (Update) መቀበያ
$update = json_decode(file_get_contents("php://input"), TRUE);

// 3. መልዕክቱ መኖሩን ማረጋገጫ
if (isset($update["message"])) {
    $chat_id = $update["message"]["chat"]["id"]; // የላኪው መለያ (ID)
    $text = $update["message"]["text"]; // የተላከው ጽሑፍ

    // 4. ለተላከው መልዕክት የሚሰጥ ምላሽ ውሳኔ (Logic)
    if ($text == "/start") {
        $reply = "ሰላም! እኔ አዲሱ ቦት ነኝ። እንዴት ልርዳዎት?";
    } else {
        $reply = "የላኩት መልዕክት ደርሶኛል። የላኩት ጽሑፍ: " . $text;
    }

    // 5. ምላሹን ወደ ቴሌግራም መልሶ መላኪያ
    $sendUrl = $apiUrl . "/sendMessage?chat_id=" . $chat_id . "&text=" . urlencode($reply);
    file_get_contents($sendUrl);
}
?>
