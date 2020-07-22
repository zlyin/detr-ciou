# detr-ciou
(Unofficial) Complete IOU loss and Distance IOU loss for DETR transformer object detection


## Instructions for use
All that is needed is a one line change to point it to the new loss function:

1 - Save box_ops.py file as detr/util/box_ops.py

2 - Open detr/models/detr.py

3 - Look for the function loss_boxes, (approx line 159 as of this writing)

4 - Comment out this line: </br> loss_giou = 1 - torch.diag(box_ops.generalized_box_iou(

5 - Insert this line in its place: </br> loss_giou = 1 - torch.diag(box_ops.complete_box_iou(

6 - Make sure it looks syntactically correct, then save
