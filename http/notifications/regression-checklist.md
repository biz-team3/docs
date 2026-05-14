# Notification Regression Checklist

Notification은 posts, comments, likes, follows 상태 변경과 같이 움직여야 한다.
아래 항목은 알림 관련 수정 후 최소 수동 검증 기준이다.

## Likes

- 다른 사용자의 게시물에 좋아요를 누르면 게시물 작성자에게 `LIKE` 알림이 생긴다.
- 좋아요를 취소하면 해당 `LIKE` 알림이 사라지고 summary badge가 감소한다.
- 좋아요 취소 후 다시 좋아요를 누르면 새 unread `LIKE` 알림이 다시 생긴다.
- 내 게시물에 내가 좋아요를 눌러도 알림은 생기지 않는다.

## Comments

- 다른 사용자의 게시물에 댓글을 쓰면 게시물 작성자에게 `COMMENT` 알림이 생긴다.
- 댓글을 삭제하면 해당 댓글의 `COMMENT` 알림이 사라지고 summary badge가 감소한다.
- 같은 게시물에 같은 사용자가 여러 댓글을 남긴 뒤 하나만 삭제해도 다른 댓글 알림은 유지된다.
- 댓글 수정/삭제는 작성자만 가능해야 한다.

## Posts

- 알림 패널에서 게시글 상세를 연 뒤 게시글을 삭제하면 패널 목록과 badge가 즉시 갱신된다.
- 삭제된 게시글을 target으로 하는 `LIKE` / `COMMENT` 알림은 목록과 summary에서 빠진다.
- 게시글 삭제는 작성자만 가능해야 한다.

## Follow Requests

- private 계정에 팔로우 요청을 보내면 버튼이 `요청됨` 상태가 된다.
- `요청됨` 버튼을 다시 누르면 pending follow request가 취소되고 버튼이 `팔로우` 상태로 돌아온다.
- 받은 팔로우 요청을 모두 수락/거절하면 알림 패널의 팔로우 요청 row와 프로필 이미지 fallback이 사라진다.
- 팔로우 요청 수락 후 `FOLLOW` 알림은 `actorUserId=requester`, `targetId=receiver` 의미를 지킨다.

## Panel State

- 알림 항목 클릭 후 read 상태와 summary badge가 동기화된다.
- 알림 패널 안에서 follow/unfollow 또는 post detail action을 수행한 뒤 패널 목록이 다시 조회된다.
